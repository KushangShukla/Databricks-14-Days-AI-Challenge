📅 Day 2 – Databricks Workspace, Notebooks & DBFS

🚀 Databricks 14-Day Challenge – Day 2

Day 2 transitions from conceptual understanding (Day 1) to platform familiarity.
The focus is on understanding how Databricks Workspace, Notebooks, Clusters, and DBFS work together to support scalable data engineering workflows.

This day builds the operational foundation needed before writing serious Spark pipelines.

🧠 Topics Covered
1️⃣ Databricks Workspace Overview

Central environment to manage:

Notebooks

Clusters

Jobs

Data

Enables collaboration between data engineers, analysts, and ML engineers

2️⃣ Databricks Notebooks

Interactive notebooks supporting:

Python (PySpark)

SQL

Scala

Used for:

Data exploration

ETL pipelines

Testing transformations

Tight integration with Apache Spark

3️⃣ Clusters – The Compute Layer

Clusters provide the compute power to run Spark jobs

Key concepts:

Driver & Worker nodes

Auto-scaling

Auto-termination

Compute is separate from storage, enabling flexibility & cost optimization

4️⃣ DBFS (Databricks File System)

Distributed storage abstraction on top of cloud storage

Used to:

Store raw files (CSV, JSON, Parquet)

Persist intermediate data

Acts as the entry point for Bronze-layer data

5️⃣ Data Flow Mental Model
Cloud Storage → DBFS → Spark Processing → Delta Tables


This mental model is critical before implementing Medallion Architecture.

🧵 Learning Method Used

🔍 Explore UI & platform components

🧠 Build intuition before heavy coding

🧵 Document learnings via Twitter/X thread

🧱 Prepare groundwork for Spark transformations

🔗 Day 2 Twitter/X Thread

👉 Day 2 Learning Thread:
https://x.com/KushangShukla/status/2009965554325733509?s=20

The thread covers:

Workspace components explained simply

Role of notebooks & clusters

Why DBFS matters in real pipelines

🎯 Outcome of Day 2

By the end of Day 2, I was able to:

Navigate Databricks Workspace confidently

Understand how notebooks execute on clusters

Use DBFS as a data ingestion layer

Visualize end-to-end data flow inside Databricks

This sets the stage for hands-on Spark coding and data ingestion in Day 3.