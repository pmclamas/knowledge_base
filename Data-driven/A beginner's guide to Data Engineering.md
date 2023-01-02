A data scientist's capability to convert data into value is largely correlated with the stage of the company's data infrastructure as well as how mature its data warehouse is.

This guide is heavily designed around Airflow, batch data processing, and SQL-like languages.

Maintain critical pipelines to track how many users visited a site, how much time each reader spents reading contents, and how often people liked or retweeted content.

I realized that my frustration was rooted in my very little understanding of how real life data projects actually work. I was thrown into the wild west of raw data, far away from the comfortable land of pre-processed, tidy .csv files, and I felt unprepared and uncomfortable working in an environment where this is the norm. I adapted to this new reality, albeit slowly and gradually.

Over time, I discovered the concept of instrumentation, hustled with machine-generated logs, parsed many URLs and timestamps, and learned SQL.

Nowadays, I understand counting carefully and intelligently is what analytics is largely about, and this type of foundational work is especially important when we live in a world filled with constant buzzwords and hypes.

_**The Hierarchy of Analytics**_

"Think of Artificial Intelligence as the top of a pyramid of needs. Yes, self-actualization (AI) is great, but you first need food, water, and shelter (data literacy, collection, and infrastructure)."

Monica Rogati

Before a company can optimize the business more efficiently or build data products more intelligently, layers of foundational work need to be built first.

![https://s3-us-west-2.amazonaws.com/secure.notion-static.com/556110cc-c7ce-44ff-9b77-1bd1bc4aa96e/Screenshot_2020-11-18_at_11.55.00.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/556110cc-c7ce-44ff-9b77-1bd1bc4aa96e/Screenshot_2020-11-18_at_11.55.00.png)

Unfortunately, many companies do not realize that most of our existing data science training programs, academic or professional, tend to focus on the top of the pyramid knowledge. Even for modern courses that encourage students to scrape, prepare, or access raw data through public APIs, most of them do not teach students how to properly design table schemas or build data pipelines. As a result, some of the critical elements of real-life data science projects are lost in translation.

Those who have the skill and experience to build foundations for data-intensive applications will be on the rise.

"Data engineering field could be thought of as a superset of business intelligence and data warehousing that brings more elements from software engineering. This discipline also integrates specialization around the operation of so called "big data" distributed systems, along with concepts around the extended Hadoop ecosystem, stream processing, and in computation at scale.

(by Maxime Beauchemin, original author of Airflow)

Among the many valuable things that data engineers do, one of their highly sought-after skills is the ability to design, build, and maintain data warehouses.

A data warehouse is a place where raw data is transformed and stored in query-able forms.

![https://s3-us-west-2.amazonaws.com/secure.notion-static.com/4ac8256e-3df5-449b-9b31-3ef4ead431d0/Screenshot_2020-11-18_at_17.11.19.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/4ac8256e-3df5-449b-9b31-3ef4ead431d0/Screenshot_2020-11-18_at_17.11.19.png)

In many ways, data warehouses are both the engine and the fuel that enables higher level analytics, be it business intelligence, online experimentation, or machine learning.

Without these foundational warehouses, every activity related to data science becomes either too expensive or not scalable.

_**ETL: Extract, Transform, and Load**_

These three conceptual steps are how most data pipelines are designed and structured. They serve as a blueprint for how raw data is transformed to analysis-ready data.

-   _**Extract:**_ this is the step where sensors wait for upstream data sources to land (e.g. a upstream source could be machine or user-generated logs, relational database copy, external dataset, etc). Upon available, we transport the data from their source locations to further transformations.
-   _**Transform:**_ this is the heart of any eTL job, where we apply business logic and perform actions such as filtering, grouping, and aggregation to translate raw data into analysis-ready datasets. This step requires a great deal of business understanding and domain knowledge.
-   _**Load:**_ finally, we load the processed data and transport them to a final destination. Often, this dataset can be either consumed directly by end-users or it can be treated as yet another upstream dependency to another ETL job, forming the so called [data lineage](https://en.wikipedia.org/wiki/Data_lineage).

[Data lineage includes the data origin, what happens to it and where it moves over time. Data lineage gives visibility while greatly simplifying the ability to trace errors back to the root cause in a data analytics process.]

While all ETL jobs follow this common pattern, the actual jobs themselves can be very different in usage, utility, and complexity. Here is a very simple toy example of an Airflow job:

```python
"""
A DAG definition file in Airflow, written in Python.
"""
from datetime import datetime, timedelta
from airflow.models import DAG  # Import the DAG class
from airflow.operators.bash_operator import BashOperator
from airflow.operators.sensors import TimeDeltaSensor

default_args = {
    'owner': 'you',
    'depends_on_past': False,
    'start_date': datetime(2018, 1, 8),
}

dag = DAG(
    dag_id='anatomy_of_a_dag',
    description="This describes my DAG",
    default_args=default_args,
    schedule_interval=timedelta(days=1))   # This is a daily DAG.

# t0 and t1 are examples of tasks created by instantiating operators
t0 = TimeDeltaSensor(
    task_id='wait_a_second',
    delta=timedelta(seconds=1),
    dag=dag)

t1 = BashOperator(
    task_id='print_date_in_bash',
    bash_command='date',
    dag=dag)

t1.set_upstream(t0)
```

[Source](https://artwr.github.io/airflow-workshop-dataengconf-sf-2017/index.html): Arthur Wiedmer’s workshop from DataEngConf SF 2017

The example above simply prints the date in bash every day after waiting for a second to pass after the execution date is reached, but real-life ETL jobs can be much more complex. For example, we could have an ETL job that extracts a series of CRUD operations from a production database and derive business events such as a user deactivation. Another example is a batch ETL job that computes features for a machine learning model on a daily basis to predict whether a user will churn in the next few days. The possibilities are endless!

_**Choosing ETL frameworks**_

In the world of batch data processing, there are a few obvious open-sourced contenders at play. To name a few: Linkedin open sourced Azkaban to make managing Hadoop job dependencies easier. Spotify open sourced Python-based framework Luigi in 2014, and Airbnb open sourced Airflow, also Python-based, in 2015.

Different frameworks have different strengths and weaknesses. (see [here](http://bytepawn.com/luigi-airflow-pinball.html) and [here](https://www.quora.com/Which-is-a-better-data-pipeline-scheduling-platform-Airflow-or-Luigi)).

Regardless of the framework that you choose to adopt, a few features are important to consider:

-   **Configuration:** ETLs are naturally complex, and we need to be able to succinctly describe the data flow of a data pipeline. Nowadays, the concept of 'configuration as code' is gaining popularity, because it allows users to expressively build pipelines programmatically that are customizable.
-   **UI, Monitoring, Alerts:** long running batch processes inevitably can run into errors (e.g. cluster failures) even when the job itself does not have bugs. As a result, monitoring and alerting are crucial in tracking the progress of long running processes. How well does a framework provide visual information for job progress? Does it surface alerts or warnings in a timely and accurate manner?
-   Backfilling: once a data pipeline is built, we often need to go back in time and re-process the historical data. Ideally, we do not want to build two separate jobs, one for backfilling historical data and another for computing current or future metrics. How easy does a framework support backfilling? Can it do so in a way that is standardized, efficient, and scalable? All these are important questions to consider.

Washington Post Labs - ETLs were mostly scheduled primitively in Cron and jobs are organized as Vertica scripts.

Twitter - ETL jobs were built in Pig whereas nowadays they are all written in Scalding, scheduled by Twitter's own orchestration engine.

Airbnb - Data pipelines are mostly written in Hive using Airflow.

**Two Paradigms: SQL vs. JVM-Centric ETL**

Different companies might pick drastically different tools and frameworks for building ETLs, and it can be very confusing to decide which tools to invest in as a new data scientist.

-   _**JVM-centric ETL -**_ is typically built in a JVM-based language (like Java or Scala). Engineering data pipelines in these JVM languages often involves thinking data transformation in a more imperative manner, e.g. in terms of key-value pairs. Writing User Defined Functions (UDFs) are less painful because one does not need to write them in a different language, and testing jobs can be easier for the same reason. This paradigm is quite popular among engineers.
-   _**SQL-centric ETL -**_ is typically built in languages like SQL, Presto, or Hive. ETL jobs are often defined in a declarative way, and almost everything centers around SQL and tables. Writing UDFs sometimes is troublesome because one has to write it in a different language (e.g. Java or Python), and testing can be a lot more challenging due to this. This paradigm is popular among data scientists.

As a new Data Scientist, you can learn much more quickly about data engineering when operating in the SQL paradigm. Because learning SQL is much easier than learning Java or Scala, and you can focus your energy on learning best practies than learning new concepts in a new domain on top of a new language.

**Data Modeling**

When a user interacts with a product like Medium, her information, such as her avatar, saved posts, and number of views are all captured by the system. In order to serve them accurately and on time to users, it is critical to optimize the production databases for Online Transaction Processing (OLTP).

When it comes to building an Online Analytical Processing System (OLAP), the objective is rather different. The designer need to focus on insight generation, meaning analytical reasoning can be translated into queries easily and statistics can be computed efficiently. This analytics-first approach often involves a design process called data modeling.

**Data Modeling, Normalization, and Star Schema**

Generally speaking, normalized tables have simpler schemas, more standardized data, and carry less redundancy. However, a proliferation of smaller tables also means that tracking data relations requires more diligence, querying patterns become more complex (more Joins), and there are more ETL pipelines to maintain.

On the other hand, it is often much easier to query from a denormalized table (aka a wide table), because all of the metrics and dimensions are already pre-joined. Given their larger sizes, however, data processing for wide tables is slower and involves more upstream dependencies. This makes maintenance of ETL pipelines more difficult because the unit of work is not as modular.

Among the many design patterns that try to balance this trade-off, one the most commonly-used patterns, is called Star Schema. This design focuses on building normalized tables, specifically fact and dimension tables. When needed, denormalized tables can be built from these smaller normalized tables. This design strives for a balance between ETL maintainability and ease of analytics.

_**Fact & Dimension Tables**_

-   _**Fact Tables -**_ typically contain point-in-time transactional data. Each row in the table can be extremely simple and is often represented as a unit of transaction. Because of their simplicity, they are often the source of truth tables from which business metrics are delivered. (e.g. fact tables can track transaction-like events such as bookings, reservations, alterations, cancellations, and more).
-   _**Dimension Tables -**_ typically contain slowly changing attributes of specific entities, and attributes sometimes can be organized in a hierarchical structure. These attributes are often called "dimensions", and can be joined with the fact tables, as long as there is a foreign key available in the Fact table.

Below is a simple example of how fact tables and dimension tables (both are normalized tables) can be joined together to answer basic analytics question such as how many bookings occurred in the past week in each market.

```python
SELECT
    b.dim_market
  , SUM(a.m_bookings) AS m_bookings
FROM (
  SELECT
      id_listing
    , 1          AS m_bookings
    , m_a        # not used (for illustration only)
    , m_b        # not used (for illustration only)
    , m_c        # not used (for illustration only)
  FROM
    fct_bookings
  WHERE
    ds BETWEEN '{{ last_sunday }}' AND '{{ this_saturday }}'
) a 
JOIN (
  SELECT
      id_listing
    , dim_market
    , dim_x      # not used (for illustration only)
    , dim_y      # not used (for illustration only)
    , dim_z      # not used (for illustration only)
  FROM
    dim_listings
  WHERE
    ds BETWEEN '{{ latest_ds }}'
) b
ON (a.id_listing = b.id_listing)
GROUP BY
  b.dim_market
;
```

Normalized tables can be used to answer ad-hoc questions or to build denormalized tables.

_**Data Partitioning & Backfilling Historical Data**_

In an era where data storage cost is low and computation is cheap, companies now can afford to store all of their historical data in their warehouses rather than throwing it away. The advantage of such an approach is that companies can re-process historical data in response to new changes as they see fit.

_**Data Partitioning by Datestamp**_

With so much data readily available, running queries and performing analytics can become inefficient over time. In addition to following SQL best practices such as "filter early and often", "project only the fields that are needed", one of the most effective techniques to improve query performance is to partition data.

The basic idea behind data partitioning is rather simple - instead of storing all the data in one chunk, we break it up into independent, self-contained chunks. Data from the same chunk will be assigned with the same partition key, which means that any subset of the data can be looked up extremely quickly. This technique can greatly improve query performance.

In particular, one common partition key to use is datestamp (ds for short). First, in data storage system like S3, raw data is often organized by datestamp and stored in time-labeled directories.

Furthermore, the unit of work for a batch ETL job is typically one day, which means new date partitions are created for each daily run. Finally, many analytical questions involve counting events that occurred in a specified time range, so querying by datestamp is a very common pattern.

_**Backfilling Historical Data**_

Another important advantage of using datestamp as the partition key is the ease of data backfilling. When a ETL pipeline is built, it computes metrics and dimensions forward, not backward. Often, we might desire to revisit the historical trends and movements. In such cases, we would need to compute metric and dimensions in the past - we called this process _data backfilling_.

Backfilling is so common that Hive built in the functionality of dynamic partitions, a construct that perform the same SQL operations over many partitions and perform multiple insertions at once.

The beauty of dynamic partitions is that we wrap all the same work that is needed with a 'GROUP BY ds' and insert the results into the relevant ds partitions all at once. This query pattern is very powerful.

**The Anatomy of an Airflow Pipeline**

Now that we have learned about the concept of fact tables, dimension tables, date partitions, and what it means to do data backfilling, let's crystalize these concepts and put them in an actual Airflow ETL job.

_**Defining the Directed Acyclic Graph (DAG)**_

As mentioned earlier, any ETL job, at its core, is built on top of three building blocks: Extract, Transform, and Load. As simple as it might sound conceptually, ETL jobs in real life are often complex, consisting of many combinations of E, T, and L tasks. As a result, it is often useful to visualize complex data flows using a graph. Visually, a node in a graph represents a task, and an arrow represents the dependency of one task on another. Given that data only needs to be computed once on a given task and the computation then carries forward, the graph is directed and acyclic. This is why Airflow jobs are commonly referred to as DAGs (Directed Acyclic Graphs).

One of the clever designs about Airflow UI is that it allows any users to visualize the DAG in a graph view, using code as configuration. The author of a data pipeline must define the structure of dependencies among tasks in order to visualize them. This specification is often written in a file called the DAG definition file, which lays out the anatomy of an Airflow job.

_**Operators: Sensors, Operators, and Transfers**_

While DAGs describe how to run a data pipeline, operators describe what to do in a pipeline. Typically, there are three broad categories of operators:

-   _**Sensors:**_ waits for a certain time, external file, or upstream data source
-   _**Operators:**_ triggers a certain action (e.g. run a bash command, execute a python function, or execute a Hive query, etc).
-   _**Transfers:**_ moves data from one location to another

_**Sensors**_ unblock the data flow after a certain time has passed or when data from an upstream data source becomes available.

_**Operators**_ trigger data transformations, which corresponds to the Transform step. Because Airflow is open-source, contributors can extend 'BaseOperator' class to create custom operators as they see fit. The most common operator used is 'HiveOperator' (to execute hive queries), but we also use 'PythonOperator' (e.g. to run a Python script) and 'BashOperator' (e.g. to run a bash script, or even a fancy Spark job). The possibilities are endless here!

We also have special operators that _**Transfers**_ data from one place to another, which often maps to the Lead step in ETL.

**A simple example**

Below is a simple example that demonstrate how to define a DAG definition file, instantiate a Airflow DAG, and define the corresponding DAG structure using the various operators.

```python
"""
A DAG docstring might be a good way to explain at a high level
what problem space the DAG is looking at.
Links to design documents, upstream dependencies etc
are highly recommended.
"""
from datetime import datetime, timedelta
from airflow.models import DAG  # Import the DAG class
from airflow.operators.sensors import NamedHivePartitionSensor
from airflow.operators.hive_operator import HiveOperator

### You can import more operators as you see fit!
# from airflow.operators.bash_operator import BashOperator
# from airflow.operators.python_operator import PythonOperator

# setting some default arguments for the DAG
default_args = {
    'owner': 'you',
    'depends_on_past': False,
    'start_date': datetime(2018, 2, 9),
}

# Instantiate the Airflow DAG
dag = DAG(
    dag_id='anatomy_of_a_dag',
    description="This describes my DAG",
    default_args=default_args,
    schedule_interval=timedelta(days=1))   # This is a daily DAG.

# Put upstream dependencies in a dictionary
wf_dependencies = {
    'wf_upstream_table_1': 'upstream_table_1/ds={{ ds }}',
    'wf_upstream_table_2': 'upstream_table_2/ds={{ ds }}',
    'wf_upstream_table_3': 'upstream_table_3/ds={{ ds }}',
}

# Define the sensors for upstream dependencies
for wf_task_id, partition_name in wf_dependencies.iteritems():
    NamedHivePartitionSensor(
        task_id=wf_task_id,
        partition_names=[partition_name],
        dag=dag
    )

# Put the tasks in a list
tasks = [
    ('hql', 'task_1'),
    ('hql', 'task_2'),
]

# Define the operators in the list above
for directory, task_name in tasks:
    HiveOperator(
        task_id=task_name,
        hql='{0}/{1}.hql'.format(directory, task_name),
        dag=dag,
    )

# Put the dependencies in a map
deps = {
    'task_1': [
        'wf_upstream_table_1',
        'wf_upstream_table_2',
    ],
    'task_2': [
        'wf_upstream_table_1',
        'wf_upstream_table_2',
        'wf_upstream_table_3',
    ],
}

# Explicitly define the dependencies in the DAG
for downstream, upstream_list in deps.iteritems():
    for upstream in upstream_list:
        dag.set_dependency(upstream, downstream)
```

When the DAG is rendered, we see the following graph view:

![https://s3-us-west-2.amazonaws.com/secure.notion-static.com/4038a391-47f1-4ea2-8256-22d549bc562d/Screenshot_2020-11-23_at_11.10.10.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/4038a391-47f1-4ea2-8256-22d549bc562d/Screenshot_2020-11-23_at_11.10.10.png)

**ETL Best practices to follow**

Writing Airflow jobs that are succinct, readable, and scalable requires practice. ETL aren't just a series of mundane mechanical tasks that has to be done. Learning ETLs best practices, you will start to appreciate good ETLs and how beautiful they can be.

Below is a non-exhaustive list of principles that good ETL pipelines should follow:

-   _**Partition Data Tables:**_ data partitioning can be especially useful when dealing with large-size tables with a long history. When data is partitioned using datestamps, we can leverage dynamic partitions to parallelize backfilling.
    
    ![https://s3-us-west-2.amazonaws.com/secure.notion-static.com/baeaf355-ff0b-421e-944e-f7e0e443c647/Screenshot_2020-11-23_at_11.16.11.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/baeaf355-ff0b-421e-944e-f7e0e443c647/Screenshot_2020-11-23_at_11.16.11.png)
    
-   _**Load Data Incrementally:**_ this principle makes your ETL more modular and manageable, especially when building dimension tables from the fact tables. In each run, we only need to append the new transactions to the dimension table from previous data partition instead of scanning the entire fact history.
    

```python
-- Not Recommended Approach: Scan the entire table and rebuild everyday
INSERT OVERWRITE TABLE dim_total_bookings PARTITION (ds = '{{ ds }}')
SELECT
     dim_market
  ,  SUM(m_bookings) AS m_bookings
FROM
  fct_bookings
WHERE
  ds <= '{{ ds }}' -- this is expensive, and can quickly run into scale issue
GROUP BY
  dim_market
;

-- Recommended Approach: Incremental Load
INSERT OVERWRITE TABLE dim_total_bookings PARTITION (ds = '{{ ds }}')
SELECT
    dim_market
  , SUM(m_bookings) AS m_bookings
FROM (
  SELECT
      dim_market
    , m_bookings
  FROM
    dim_total_bookings            -- a dim table
  WHERE
    ds = DATE_SUB('{{ ds }}', 1)  -- from the previous ds

  UNION
  
  SELECT
      dim_market
    , SUM(m_bookings) AS m_bookings
  FROM
    fct_bookings                  -- a fct table
  WHERE
    ds = '{{ ds }}'               -- from the current ds
  GROUP BY
     dim_market
) a
GROUP BY
  dim_market
;
```

-   _**Enforce Idempotency:**_ many data scientists rely on point-in-time snapshots to perform historical analysis. This means the underlying source table should not be mutable as time progresses, otherwise we would get a different answer. Pipeline should be built so that the same query, when run against the same business logic and time range, returns the same result. This property has a fancy name called Idempotency.
-   _**Parameterize Workflow:**_ just like how templates greatly simplified the organization of html pages, Jinja can be used in conjunction with SQL. As we mentioned earlier, one common usage of Jinja template is to incorporate the backfilling logic into a typical Hive query.

```python
{%- if backfill %}
INSERT OVERWRITE TABLE bookings_summary PARTITION (ds)
{%- else %}
INSERT OVERWRITE TABLE bookings_summary PARTITION (ds = '{{ ds }}')
{%- endif %}
SELECT
    dim_market
  , SUM(m_bookings) AS m_bookings
  {%- if backfill %}
  , ds
  {%- endif %}
FROM
  fct_bookings
WHERE
{%- if backfill %}
  ds BETWEEN '{{ start_date }}' AND '{{ end_date }}'
{%- else %}
  ds = '{{ ds }}'
{%- endif %}
GROUP BY
    dim_market
{%- if backfill %}
  , ds
{%- endif %}
;
```

-   _**Add data checks early and often:**_ when processing data, it is useful to write data into a staging table, check the data quality, and only then exchange the staging table with the final production table. We call this the stage-check-exchange paradigm. Checks in this 3-step paradigm are important defensive mechanisms - they can be simple checks such as counting if the total number of records is greater than 0 or something as complex as an anomaly detection system that checks for unseen categories or outliers.
    
    ![https://s3-us-west-2.amazonaws.com/secure.notion-static.com/9ddaecf9-e309-460d-8cf9-ec9e99be643b/Screenshot_2020-11-23_at_11.25.27.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/9ddaecf9-e309-460d-8cf9-ec9e99be643b/Screenshot_2020-11-23_at_11.25.27.png)
    
-   **Build useful alerts & monitoring system:** since ETL jobs can often take a long time to run, it's useful to add alerts and monitoring to them so we do not have to keep an eye on the progress of the DAG constantly. Different companies monitor DAGs in many creative ways, from regularly use of EmailOperators to send alert emails for jobs missing SLAs, to use of alerts to flag experiment imbalances.
    

Typically, as companies climb up the [hierarchy of data analytics](https://hackernoon.com/the-ai-hierarchy-of-needs-18f111fcc007) and scale beyond a small team, complexity and development cost often increase. At Airbnb, we have more than 100+ contributors who authored Airflow pipelines. This makes enforcing ETL best practices, upholding data quality, and standardizing workflows increasingly challenging. Luckily, one of the antidotes to complexity is the power of **abstraction**. This principle, of course, is no exception when it coms to data engineering.

In data engineering, abstraction often means identifying and automating ETL patterns that are common in peoples' workflows. We will define the concept of a data engineering framework. We will dissect typical design patterns for building such frameworks, and finally, highlight a few specific examples frequently used at Airbnb.

_**A common scenario**_

Suppose your company is now big enough to have several teams working on different parts of its product. Each team has its own OKR (Objectives and Key Results), product roadmap, and key performance indicators. As the embedded data scientist on the team, you are responsible for creating an analytics dashboard to track how the business is doing.

You start with data modeling and schema design. You identify relevant fact and dimension tables in order to calculate meaningful metrics organized by various useful dimensional cuts.

You spend quite some time joining the tables to create a final denormalized table, and finally you backfill all the historical data. While this work is impactful, after working on a few dashboards, you have come to feel that the ETL workflow has become rather repetitive. In fact, many data scientists you talk to at the company are also creating dashboards using a similar workflow for their respective teams.

![https://s3-us-west-2.amazonaws.com/secure.notion-static.com/37d2cbc1-285f-4265-9f94-49d35b77d382/Screenshot_2020-11-23_at_12.59.47.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/37d2cbc1-285f-4265-9f94-49d35b77d382/Screenshot_2020-11-23_at_12.59.47.png)

[Welcome](https://superset.apache.org/)

Not surprisingly, with product launches comes experiment deep dives - you carefully join an experiment assignment table with a fact table in order to aggregate user-level metrics. You compute test statistics from different treatment arms in order to calculate p-values and confidence intervals for your experiment. After talking to a few other data scientists, you once again realized that this is yet another workflow that is common among data scientists. In fact, it feels like a lot of what data scientists do on a day-to-day basis can be bucketed into a few distinct but common workflows.

**From pipeline to frameworks**

Airflow DAGs can be arbitrarily complex. Sometimes, the data computation even follows a control-flow like logic. For example, if you are interested in branching out the data flow after a specific conditional check, you can apply the 'BranchPythonOperator'. If you want a workflow to continue only if a condition is met, you can use the 'ShortCircuitOperator'. These operators, combined with the principle of _**configuration as code**_ are what makes Airflow ETLs versatile and felxible.

Our discussion so far has been limited to the design of a single, standalone pipeline, but we can apply the same principle to pipeline generation - a way to programmatically and dynamically generate DAGs on the fly. This is essentially what a data engineering framework does: it generates different instantiations of Airflow DAGs that automate data workflows.

[Here](https://news.ycombinator.com/item?id=13761071) is how the original author of Airflow, describes it:

"To build workflows dynamically from code...A very simple example would be an Airflow script that reads a YAML config file with a list of table names, and creates a little workflow for each table, that may do things like loading the table into a target database, perhaps apply rules from the config file around sampling, data retention, anonymization...Now you have this abstraction...you can create new chunks of workflows without doing much work. It turns out there are tons of use cases for this type of approach."

These tools are important because they enable data scientists to move up the data value chain much more quickly than they otherwise could.

-   Imagine that when an experiment reporting framework auto-generates user-level metrics and computes statistics for an experiment, data scientists could now devote more time to analyzing changes in key metrics, interpreting user behavior, and highlighting the impact of product changes.
-   Similarly, when a metrics framework automatically generates OLAP tables on the fly, data scientists can spend more time understanding trends, identifying gaps, and relaying product changes to business changes.
-   Another example is a framework that abstracts away the engineering work required for productionizing an offlinw batch ML model. Data scientists no longer need to worry about package dependencies, setting up a virtual environment, or deployment. They can spend time on modeling instead.

The implication of these frameworks is profound because they drastically improve how data scientists work. These are precisely technologies that enable data scientists to provide value at scale.

**Design patterns for data engineering frameworks**

_"When you have done certain tasks enough times, you start to see patterns that can be automated."_

As useful as they are, Data Engineering frameworks are rarely born out of thin air. When you see your work as workflows, new possibilities arise.

When thinking about which workflow to automate, the framework designer needs to start by thinking about the end user's experience. There are generally three layers of a well-designed data engineering framework: the _**input**_ layer, the _**data processing**_ layer, and the _**output**_ layer.

![https://s3-us-west-2.amazonaws.com/secure.notion-static.com/5cec0724-ec14-4827-8cf3-d52c4ace0c5f/Screenshot_2020-11-23_at_13.46.48.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/5cec0724-ec14-4827-8cf3-d52c4ace0c5f/Screenshot_2020-11-23_at_13.46.48.png)

-   _**Input:**_ this is where an end user specifies how their DAGs should be configured. User experience really matters here. Typically, the input could be a static configuration file (e.g. YAML), or it could be something as elaborate as a web UI. The goal here is to capture user needs.
-   _**Data processing:**_ this is the core of any data engineering framework, where ETL pipelines are instantiated dynamically. The code that achieves this is generally referred to as a DAG factory, which whimsically captures the notion that DAGs are being created one at a time, like in a factory.
-   _**Output:**_ The DAGs generated from the previous step create derived data, and the output is often saved in a downstream Hive table, presented in a well-designed UI/visualization layer, or simply consumed by downstream pipelines or frameworks.

(when reding the sections below, keep in mind which workflow each framework is trying to automate and pay attention to the input and output layers of the framework.)

**Incremental Computation Framework**

It is quite common for data scientists to calculate computationally intensive metrics like a cumulative sum or the time since the first or last event. For example, we might wish to report the total number of users who ever engaged with a new product or to compute a histogram of days since users have last returned. The naive approach would be to query a fact table and take the sum, max, or min over all date partitions in order to calculate these desired metrics. However, this querying pattern is rather inefficient.

Why? This solution violates the ETL principle of load data incrementally since the required computation scans the entire fact table. Ideally, we would build a summary table to pre-compute these metrics so an end-user only needs to reference the metric in a single or latest date partition of the summary table.

This is pattern is very common.

-   _**Input:**_ A HOCON configuration file where a user specifies which metrics or events to pre-compute, which subject key to group by, and which fact table to query from in order to build the summary table.
-   _**Data Processing:**_ an Airflow script that builds the summary table incrementally, namely, union the summary table from the previous date partition with today's fact table to update the expensive metrics.

`cumsum_metric_today = f (cumsum_metric_yesterday, metric_today)`, where f can be a sum, min/max, or any other aggregation functions.

-   _**Output:**_ optimized summary table where cumulative sum, days since first/last event or other expensive metrics can be queried from one and only one single date partition from the summary table.

**What workflow does this framework automate?** It helps users to avoid inefficient querying patterns and automates away the tedious aggregation that we otherwise would need to do, one date partition at a time.

**Backfill Framework**

Backfilling is an important but time-consuming step in any data engineering work. Once an ETL pipeline is built, we need to retrospectively visit earlier data in order to reconstruct history. Some of the backfilling strategies we have discussed include dynamic partitions and baking backfill logic into SQL using [Jinja templates](https://jinja.palletsprojects.com/en/2.10.x/). However, even with these techniques, backfilling can still be tedious.

For example, if we need to backfill a few years worth of data, it would be much more efficient to break and parallelize such a task into mini-backfills. However, managing these long-running parallel processes can be rather cumbersome. In addition, we often need to perform sanity checks before inserting backfilled data into a production table. Given that backfilling is such a common but far too often unpleasant experience, we built a _**Backfill Framework**_ to automate this workflow:

-   _**Input:**_ A simple UI where users can specify the job name, the 'start_date' and 'end_date' of the backfill job, how many processes we want to parallelize the backfill for, and how many days each process should backfill for.
-   _**Data Processing:**_ once a user specifies how the backfill job would be run, the framework creates a Airflow pipeline that automatically parallelizes the backfill tasks, performs sanity-checks, and swaps staging tables with production tables.
-   _**Output:**_ a fully backfilled table ready for consumption.

**What workflow does this framework automate?** It automates away many of the ad-hoc backfilling scripts people have to run on their own machines. It automates quality assurance by setting up automatic comparison. Finally, it swaps the staging table with the production table after QA tests.

**Global Metrics Framework**

Up until recently, data scientists at Airbnb spent quite a lot of time when it came to building ETLs for analytics and dashboards. As we discussed earlier, a lot of work here is to identify the correct data sources, to define metrics and dimensions, and to create the final denormalized tables. While different teams might have different key performance metrics and, as a result, different fact tables, important dimensions for the business are usually quite consistent and slowly changing.

For example, data scientists who work on the host-side of the marketplace typically care about dimensional cuts such as the listing's market, type, or capacity. Similarly, data scientists on the guest-side care about dimensions such as guest stage, origin market, or destination market. With this insight, it became clear that a lot of ETL pipelines actually involved joins of many fact tables with a much smaller set of dimension tables. This is what motivated the creation of Global Metrics Framework.

-   _**Input:**_ a much more involved HOCON configuration file that specifies one or more metrics in an atomic fact table, dimension sets that one wishes to include in the final table, primary keys and foreign keys to be used for joins, and a slew of other useful information to track table creations.
-   _**Data Processing:**_ the framework identifies the metrics and the dimensional cuts that it needs to aggregate and cut by, joins the dimension tables with the atomic fact tables to create the denormalized tables automatically.
-   _**Output:**_ one or more Hive tables with the same set of metrics but possibly different sets of dimensions are created. This means that one or more denormalized tables can be created on the fly, and all these data sources are further made available in Druid for visualization in Superset.

**What workflow does this framework automate?** It automates away the common data engineering work that is required for the creation of denormalized tables that can be later used for dashboards, analytics, and more.

**Experimentation Reporting Framework**

Many of the data-driven technology companies have built their own internal experimentation platforms. ETL in experimentation pipelines can be very complex. They often involve several modular DAGs, each consisting of thousands of tasks.

Despite its complexity, such an investiment is often worthwhile and even necessary, because it enables product teams in the company to run hundreds or thousands of experiments concurrently without needing to hire hundreds or thousands of data scientists.

-   _**Input:**_ instead of a simple configuration file or a simple UI, a fully fledged UI is built here so users can specify the type of experiment to run, which target or secondary metrics to track, what are the experiment buckets and their relative sizes, etc. Anything that is relevant for launching and computing the experiment data is captured in this step.\
-   _**Data Processing:**_ the metrics pipeline that computes, for each experiment, the subject-level metrics and their corresponding dimensions. The sheer combinations of these metrics and dimensions are what makes the computation super complex. In fact, it is often the case that experimentation pipelines are the most complex ETL job at a company.
-   _**Output:**_ instead of a simple output table, there is a lot of downstream processing involved in this step. For example, statistics such as p-value, confidence interval, significance, and minimum detectable effect are calculated here. Depending on the maturity of the reporting framework, users might be able to do metrics capping or variance reduction. Each step requires a separate calculation before being served in the final UI.

**What workflow does this framework automate?** The hundreds and thousands of experiment deep dives that data scientists otherwise need to carry out.

**Conclusion**

By now, I hope you have come to appreciate the power of abstraction in Data Engineering frameworks. These frameworks are incredible multipliers to data scientists' workd and workflow. It was really mind-blowing when I learned about how much of my day-to-day work can be abstracted away. As a strong believer of the philosophy that analytics are built upon layers, I see these frameworks as the foundational pieces that need to be in place first.