# Practices - Data engineering

## TP - Data processing with Apache Spark
To process a large amount of data partitioned on a data lake, you can use data processing frameworks such as Apache Spark :
1. Read : https://spark.apache.org/docs/latest/sql-programming-guide.html

Some questions :
* What is Spark RDD API ?

  The Spark RDD API is the main programming abstraction in Apache Spark for working with structured and unstructured data. RDDs can be created from a variety of data sources (e.g. Hadoop Distributed File System (HDFS), local file systems, Apache Cassandra, etc.) and support a set of transformations and action operations that enable developers to manipulate data in a variety of ways. The RDD API can process data in memory or on disk, providing fault tolerance and the ability to work quickly with large data sets
* What is Spark Dataset API ?

  The Spark Dataset API is a high-level abstraction in Apache Spark for working with structured data. It has typed columns and can be manipulated using Spark SQL. Unlike DataFrame, the Dataset API supports strongly typed and functional programming, and can manipulate data using Lambda expressions. The Dataset API also supports a variety of data sources such as Hadoop Distributed File System (HDFS), Apache Cassandra and Amazon S3, as well as SQL and Spark SQL built-in functions for complex data processing and analysis. In summary, the Spark Dataset API is a very powerful abstraction for structured data processing, suitable for large-scale data processing and analysis scenarios, such as machine learning and data warehousing.
* With which languages can you use Spark ? 

  We can write Spark applications in a variety of programming languages, including Java, Scala, Python, R and SQL. Java and Scala are the native languages of Spark and provide the most complete API support.
* Which data sources or data sinks can Spark work with ?

  Spark's ability to work with a variety of data sources and data receivers (sinks), including Hadoop Distributed File System, Local File System, Apache Cassandra, Amazon S3, Apache Kafka, JDBC databases, Elasticsearch, Hive and MongoDB, makes Spark a versatile tool for big data processing and analysis.

### Analyse data with Apache Spark and Scala 
One engineering team of your company created for you a TV News data stored as JSON inside the folder `data-news-json/`.

Your goal is to analyze it with your savoir-faire, enrich it with metadata, and store it as [a column-oriented format](https://parquet.apache.org/).

1. Look at `src/main/scala/com/github/polomarcus/main/Main.scala` and update the code 

**Important note:** As you work for a top-notch software company following world-class practices, and you care about your project quality, you'll write a test for every function you write.

You can see tests inside `src/test/scala/` and run them with `sbt test`

### How can you deploy your app to a cluster of machines ?
* https://spark.apache.org/docs/latest/cluster-overview.html

  To deploy a Spark application to a cluster of machines, package the application code and dependencies into a JAR or ZIP file, install Spark on the cluster machines, set up the cluster manager, and then submit the application to the cluster manager using the spark-submit script. The cluster manager will allocate resources and start an executor process on the worker node to execute your task, while the driver runs on one of the cluster nodes to coordinate the execution of the task.

### Business Intelligence (BI)
How could use we Spark to display data on a BI tool such as [Metabase](https://www.metabase.com/) ?

Tips: https://github.com/polomarcus/television-news-analyser#spin-up-1-postgres-metabase-nginxand-load-data-to-pg

### Continuous build and test
**Pro Tips** : https://www.scala-sbt.org/1.x/docs/Running.html#Continuous+build+and+test

Make a command run when one or more source files change by prefixing the command with ~. For example, in sbt shell try:
```bash
sbt
> ~ testQuick
```