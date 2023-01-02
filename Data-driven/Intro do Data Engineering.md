**My journey to data engineering**

A couple of years ago, before becoming a data engineer, I mainly worked on database and application development (plus scale and performance testing). I loved working with RDBMS and data so much that I decided to pursue an engineering career that focuses on Big Data.

**What does a Data Engineer do?**

Data Engineers are responsible for designing, developing, and maintaining the data platform, which includes the data infrastructure, data applications, data warehouse, and data pipelines.

Data Engineers are usually divided into different groups that work with a specific part of the data platform:

-   _**Data warehouse & pipelines -**_ data warehouse engineers build batched and/or real-time data pipelines to integrate data between systems and support the data warehouse. Since the data warehouse is meant for tackling business problems, data warehouse engineers usually work closely with data analysts, scientists, or business teams that serve a specific business function.
-   _**Data infrastructure -**_ data infrastructure engineers build and maintain the very foundation of a data platform: the distributed systems that everything runs on top of. (Hadoop, for example)
-   _**Data applications -**_ data application engineers are software engineers building internal data tools and APIs. Sometimes a great internal tool may later become an open-source product of the company.

**What is a data warehouse?**

A [data warehouse](https://en.wikipedia.org/wiki/Data_warehouse) is a data storage system filled with data from various sources and is mainly used for data analysis. A company's data is often stored in different transactional systems (or even worse, as text files), and transactional data is highly normalized and suboptimal for analytics. The main reason for building a data warehouse is to store all types of data in optimized formats in a centralized place so that data scientists can analyze this data altogether. There are many databases that serve as a data warehouse, such as [Apache Hive](https://hive.apache.org/), or RedShift (AWS).

**What is a data pipeline?**

A data pipeline is a series of data processes that extract, process, and load data between different systems.

_There are two main types of data pipelines:_ batch-driven and real-time.

-   _**Batch-driven -**_ batch data pipelines only process data at a certain frequency and are often scheduled by a data orchestration tool, such as [Airflow](https://towardsdatascience.com/https-medium-com-xinran-waibel-build-data-pipelines-with-apache-airflow-808a4de79047), [Oozie](https://towardsdatascience.com/lesser-known-tips-on-apache-oozie-1e9bee9169da), or Cron. They usually process a large batch of historical data all at once, therefore taking a long time to finish and inducing more data delay at the end system. For example, a batch-based data pipeline downloads the previous day's data from an API at 12 AM every day, transforms the data, and then loads it into a data warehouse.
-   _**Real-time -**_ real-time data pipelines process new data as soon as it is available, and there is almost no delay between the source and end system. The architecture for real-time data processing is very different from that of batched pipelines because data is treated as a stream of events instead of chunks of records. For example, to rebuild the pipeline mentioned above into a real-time pipeline, an event streaming tool like [Kafka](https://www.confluent.io/what-is-apache-kafka/) is needed: a [Kafka Connector](https://www.confluent.io/product/confluent-platform/platform-ecosystem/) will stream data from the API into a Kafka topic, and a [Kafka Streams](https://docs.confluent.io/platform/current/streams/index.html) (or [Kafka Producer](https://docs.confluent.io/platform/current/clients/producer.html)) process will perform the transformation on the raw data from the Kafka topic and load the transformed data into another Kafka topic. The delay between the source API and the destination Kafka topic may be within a second!

**How is a data engineer different from a data scientist?**

Data Engineers build the data platform that enables data scientists to analyze data and train Machine Learning (ML) models. Sometimes data engineers also need to do data analysis and help data scientists integrate ML models into data pipelines. In some data teams, you might find data scientists doing data engineering work. There are several overlapped skills between data engineers and data scientists: programming, data pipelining, and data analysis.

There is an emerging role called ML Engineer that builds a bridge between both worlds. An ML Engineer wields strong skills in both engineering and machine learning and is responsible for optimizing and productionalizing ML models.

**What skills and tools to learn?**

-   _**Distributed systems:**_ Hadoop
-   _**Databases:**_ MySQL
-   _**Data processing:**_ Spark
-   _**Real-time data ecosystem:**_ Kafka
-   _**Data orchestration:**_ Airflow
-   _**Data Science & ML:**_ Pandas
-   _**Full-stack development:**_ React

Each company is leveraging different tools for its data platform. Therefore, I recommend you first learn the foundation knowledge for each core skill, then pick a popular tool to learn in-depth and understand the trade-offs between what you picked and the other tools out there. To get to the next level, you also need to know how all the tools work together in a data architecture.