Big data. Cloud data. AI training data and personally identifying data. Data is all around you and is growing every day. It only makes sense that software engineering has evolved to include data engineering, a subdiscipline that focuses directly on the transportation, transformation, and storage of data.

**What do Data Engineers do?**

Data Engineering is a vey board discipline that comes with multiple titles. It's probably best to first identify the goals of data engineering and then discuss what kind of work brings about the desired outcomes.

The ultimate goal of data engineering is to provide organized, consistent data flow to enable data-driven work,such as:

-   training machine learning models
-   doing exploratory data analysis
-   populating fields in an application with outside data

This data flow can be achieved in any number of ways, and the specific tool sets, techniques, and skills required will vary widely across teams, organizations, and desired outcomes. However, a common pattern is the data pipeline. This is a system that consists of indenpendent programs that do various operations on incoming or collected data.

Data pipelines are often distributed across multiple servers:
![[Screenshot_2020-12-28_at_13.39.09.png]]

(This image is a simplified example data pipeline to give you a very basic idea of an architecture you may encounter.)

The data can come from any source:

-   Internet of Things devices
-   Vehicle telemetry
-   real estate data feeds
-   normal user activity on a web application
-   any other collection or measurement tools you can think of

Depending on the nature of these sources, the incoming data will be processed in real-time streams or at some regular cadence in batches.

The pipeline that the data runs through is the responsibility of the data engineer. Data engineering teams are responsible for the design, construction, maintenance, extension, and often, the infrastructure that supports data pipelines. They may also be responsible for the incoming data or, more often, the [data model](https://en.wikipedia.org/wiki/Data_model) and how that data is finally stored.

Many teams are also moving toward building data platforms. In many organizations, it's not enough to have just a single pipeline saving incoming data to an SQL database somewhere. Large organizations have multiple teams that need different levels of access to different kinds of data.

For example, Artificial Intelligence (AI) teams may need ways to label and split cleaned data. Business Intelligence (BI) teams may need easy access to aggregate data and build data visualizations. Data Science teams may need database-level access to properly explore the data.

If you're familiar with web development, then you might find this structure similar to the Model-View-Controller (MVC) design pattern. With MVC, Data Engineers are responsible for the model, AI or BI teams work on the views, and all groups collaborate on the controller. Building data platforms that serve all these needs is becoming a major priority in organizations with diverse teams that rely on data access.

**What are the responsibilities of Data Engineers?**

Common customers of data engineering teams:

-   Data Science and AI teams
-   Business Intelligence or analytics teams
-   Product teams

Before any of these teams can work effectively, certain needs have to be met. In particular, the data myust be:

-   Reliably routed into the wider system
-   Normalized to a sensible data model
-   Cleaned to fill in important gaps
-   Made accessible to all relevant members

_**Data Flow**_

To do anything with data in a system, you must first ensure that it can flow into and through the system reliably. Inputs can be almost any type of data you can imagine, including:

-   Live streams of JSON or XML data
-   Batches of videos updated every hour
-   Monthly blood-draw data
-   Weekly batches of labeled images
-   Telemetry from deployed sensors

Data Engineers are often responsible for consuming this data, designing a system that can take this data as input from one or many sources, transform it, and then store it for their customers. These systems are often called ETL pipelines.

The data flow responsibility mostly falls under the Extract step. But the data engineer's responsibility doesn't stop at pulling data into the pipeline. They have to ensure that the pipeline is robust enough to stay up in the face of unexpected or malformed data, sources going offline, and fatal bugs. Uptime is very important, especially when you're consuming live or time-sensitive data.

_**Data Normalization and Modeling**_

Data flowing into a system is great. However, at some point, the data need to conform to some kind of architectural standard. Normalizing data involves tasks that make the data more accessible to users. This includes but is not limited to the following steps:

-   Removing duplicates
-   Fixing conflicting data
-   Conforming data to a specific data model

These processes may happen at different stages.

You may store unstructured data in a data lake to be used by your data science customers for exploratory data analysis. You may also store the normalized data in a relational database or a more purpose-built data warehouse to be used by the BI team in its reports.

The image below shows a modified version of the previous pipeline example, highlighting the different stages at which certain teams may access the data:
![[Screenshot_2020-12-28_at_14.40.35.png]]

In this image, you see a hypothetical data pipeline and the stages at which you'll often find different customer teams working.

If your customer is a product team, then a well-architected data model is crucial. A thoughtful data model can be the difference between a slow, barely responsive application and one that runs as if it already knows what data the user wants to access. These sorts of decisions are often the result of a collaboration between product and data engineering teams.

Data normalization and modeling are usually part of the Transform step of ETL, but they're not the only ones in this category. Another common transformative step is data cleaning.

_**Data Cleaning**_

Data Cleaning goes hand-in-hand with data normalization. Some even consider data normalization to be a subset of data cleaning. But while data normalization is mostly focused on making disparate data conform to some data model, data cleaning includes a number of actions that make the data more uniform and complete, including:

-   Casting the same data to a single type (for example, forcing strings in an integer field to be integers)
-   Ensuring dates are in the same format
-   Filling in missing fields if possible
-   Constraining values of a field to a specified range
-   Removing corrupt or unusable data

The specific actions you take to clean the data will be highly dependent on the inputs, data model, and desired outcomes. The importance of clean data, though, is constant:

-   _Data Scientists_ need it to perform accurate analyses.
-   _Machine Learning engineers_ need it to build accurate and generalizable models.
-   _Business Intelligence teams_ need it to provide accurate reports and forecasts to the business.
-   _Product teams_ need it to ensure their product doesn't crash or give faulty information to users.

The data-cleaning responsibility falls on many different shoulders and is dependent on the overall organization and its priorities. As a Data Engineer, you should strive to automate cleaning as much as possible and do regular spot checks on incoming and stored data. Your customer teams and leadership can provide insight on what constitutes clean data for their purposes.

_**Data Accessibility**_

Refers to how easy the data is for customers to access and understand. This is something that is defined very differently depending on the customer:

-   Data Science teams may simply need data that's accessible with some kind of query language.
-   Analytics teams may prefer data grouped by some metric, accessible through either basic queries or a reporting interface.
-   Product teams will often want data that is accessible through fast and straightforward queries that don't change often, with an eye toward product performance and reliability.

Many Data Engineers are finding themselves becoming platform engineers, making clear the continued importance of data engineering skills to data-driven businesses. Because data accessibility is intimately tied to how data is stored, it's a major component of the Load step of ETL, which refers to how data is stored for later use.

**What are common data engineering skills?**

Data engineering skills are largely the same ones you need for software engineering. However, there are a few areas on which data engineers tend to have a greater focus.

-   General programming concepts
-   Databases
-   Distributed systems and cloud engineering

Each of these will play a crucial role in making you a well-rounded data engineer.

_**General Programming skills**_

Data Engineering is a specialization of software engineering, so it makes sense that the fundamentals of software engineering are at the top of this list. As with other software engineering specializations, data engineers should understand design concepts such as DRY, object-oriented programming, data structures, and algorithms.

As in other specialties, there are also a few favored languages. As of this writing, the ones you see most often in data engineering are Python, Scala, and Java.

Python is popular for several reasons. One of the biggest is its ubiquity. It's also widely used by machine learning and AI teams. Another, more targeted reason for Python's popularity is its use in orchestration tools like Apache Airflow and the available libraries for popular tools like Apache Spark.

Scala is also quite popular, and like Python, this is partially due to the popularity of tools that use it, especially Apache Spark. Scala is a functional language that runs on the JVM, making it able to be used seamlessly with Java.

_**Database Technologies**_

If you're going to be moving data around, then you're going to be using databases a lot. Very broadly, you can separate database technologies into two categories: SQL and NoSQL.

SQL databases are relational database management systems (RDBMS) that model relationships and are interacted with by using Structured Query Language (SQL). These are commonly used to model data that is defined by relationships.

NoSQL typically means "everything else". These are databases that usually store nonrelational data, such as the following:

-   Key-value stores like Redis or AWS DynamoDB.
-   Document stores like MongoDB or Elasticsearch.
-   Graph databases like Neo4J.

While you won't be required to know the ins and outs of all database technologies, you should understand the pros and cons of these different systems and be able to learn one or two of them quickly.

The systems that data engineers work on are increasingly located on the cloud, and data pipelines are usually distributed across multiple servers or clusters, whether on a private cloud or not. Because of this, a prospective data engineer should understand distributed systems and cloud engineering.

_**Distributed Systems and Cloud Engineering**_

One of the major advantages of data engineering techniques such as ETL pipelines is that they lend themselves to the implementation of distributed systems.A common pattern is to have independent segments of a pipeline running on separate servers orchestrated by a message queue like RabbitMQ or **Apache Kafka**.

**It's essential to understand how to design these systems, what their benefits and risks are, and when you should use them.**

**Private cloud providers such as Amazon Web Services, Google Cloud, and Microsoft Azure are extremely popular tools for building and deploying distributed systems.**

**A basic understading of the major offerings of cloud providers as well as some of the more popular distributed messaging tools will help you find your first data engineering job. You can expect to learn these tools more in depth on the job.**

**What isn't data engineering?**

Here are some of the fields that are closely related to data engineering:

-   Data Science
-   Business Intelligence
-   Machine Learning engineering

_**Data Science**_

If data engineering is governed by how you move and organize huge volumes of data, then data science is governed by what you do with that data.

Data Scientists commonly query, explore, and try to derive insights from datasets. They may write one-off scripts to use with a specific dataset, while Data Engineers tend to create reusable programs using software engineering best practices.

Data Scientists use statistical tools along with machine learning techniques. They often work with R or Python and try to derive insights and predictions from data that will guide decision-making at all levels of a business.

Data Scientists work on a project that answers a specific research question, while a data engineering team focuses on building extensible, reusable, and fast internal products.

_**Business Intelligence**_

Is similar to Data Science, with a few important differences. Where Data Science is focused on forecasting and making future predictions, Business Intelligence is focused on providing a view of the current state of the business.

Both of these groups are served by Data Engineering teams and may even work from the same pool of data. Business Intelligence, though, is concerned with analyzing business performance and generating reports from the data. These reports then help management make decisions at the business level.

Like data scientists, business intelligence teams rely on data engineers to build the tools that enable them to analyze and report on data relevant to their area of focus.

_**Machine Learning engineering**_

Machine Learning engineers are another group you'll come into contact with often. You may do similar work to them, or you might even be embedded in a team of machine learning engineers.

Like data engineers, machine learning engineers are more focused on building reusable software, and many have a computer science background. However, they're less focused on building applications and more focused on building machine learning models or designing new algorithms to be used in models.

The models that machine learning engineers build are often used by product teams in customer-facing products. The data that you provide as a data engineer will be used for training their models, making your work foundational to the capabilities of any machine learning team you work with.

For example, a machine learning engineer may develop a new recommendation algorithm for your company's product, while a data engineer would provide the data used to train and test that algorithm.

One important thing to understand is that the field's you've looked at here often aren't clear-cut. People with a Data Science, BI, or Machine Learning background may do data engineering work at an organization, and as a data engineer, you may be called upon to asit these teams in their work.

You could find yourself rearchitecting a data model one day, building a data labeling tool another, and optimizing an internal deep learning framework after that. Good data engineers are flexible, curious, and willing to try new things.

