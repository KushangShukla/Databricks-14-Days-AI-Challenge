📅 Day 3 – First Data Loads & Spark Basics in Databricks

🚀 Databricks 14-Day Challenge – Day 3

Day 3 dives into actual hands-on work inside Databricks.
We worked with reading data into Spark, explored Spark DataFrames & Spark SQL, and performed our first transformations on structured data.
This day turns theoretical foundation into practical Spark experience.

🧠 Topics Covered
✅ Reading Data into Spark

Loaded sample datasets using:

spark.read.csv

spark.read.json

spark.read.parquet

Explored schema inference and manual schema definition

✅ Spark DataFrames

Created DataFrames from files in DBFS

Explored core operations:

show(), printSchema()

select(), filter()

count(), distinct()

✅ Spark SQL

Registered DataFrames as temporary views

Queried data using SQL syntax
E.g.:

SELECT column1, COUNT(*)
FROM table_view
WHERE column2 IS NOT NULL
GROUP BY column1

✅ First Transformations

Performed simple ETL:

Cleaned missing values

Renamed columns

Filtered records

Basic aggregations

✅ Delta Tables Intro

Introduced Delta Lake

Converted DataFrames to Delta format

Created managed & unmanaged Delta tables

🧵 Learning Method

🚀 Practice first: Load actual data

🧠 Spark concepts through action

🧵 Daily Twitter/X thread reinforces learnings

🧱 Build towards Medallion Architecture in future days

🔗 Day 3 Twitter/X Thread

👉 Day 3 Learning Thread:
https://x.com/KushangShukla/status/2010441893403120097?s=20

The thread covers:

Reading data in Spark

DataFrame basics

Spark SQL examples

Transformations & insights

🧩 Code Snippet (Example)

Here’s a simplified version of what we did in Day 3 notebooks:

# Read CSV
df = spark.read.option("header", True).csv("/FileStore/data/sample.csv")

# Show basic info
df.printSchema()
df.show(5)

# Spark SQL
df.createOrReplaceTempView("sample_view")

spark.sql("""
  SELECT category, COUNT(*) AS ct 
  FROM sample_view
  WHERE price IS NOT NULL
  GROUP BY category
  ORDER BY ct DESC
""").show()

🎯 Outcome of Day 3

By the end of Day 3, I was able to:
✅ Read different data formats into Spark
✅ Explore and query data using DataFrame & SQL
✅ Perform basic ETL transformations
✅ Create Delta tables for downstream pipelines

We’re now ready for structured pipeline development in Day 4.