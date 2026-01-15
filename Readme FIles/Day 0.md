📅 Day 0 – Setup & Data Loading (Prerequisites)

🚀 Databricks 14-Day Challenge – Day 0

Day 0 focuses on environment setup and dataset ingestion, which is a mandatory prerequisite before starting the core Databricks learning days.
The goal is to load a real-world e-commerce dataset from Kaggle directly into Databricks, ensuring the workspace, storage, and Spark environment are ready for downstream processing.

🧠 Overview

By the end of Day 0, we achieve:

A working Databricks Community Edition environment

Kaggle API integration inside Databricks

Structured storage using Databricks Volumes

Successful loading of large CSV datasets into Spark DataFrames

This dataset will be reused throughout Days 1–14.

🛠️ Step-by-Step Setup
✅ Step 1: Create Databricks Account

Visit: https://bit.ly/4nK0NTN

Sign up for Databricks Community Edition

Verify email and log in

Create a cluster (default configuration is sufficient)

✅ Step 2: Get Kaggle API Credentials

Go to https://www.kaggle.com/

Log in → Profile Picture → Account

Scroll to API

Click Create New API Token

Download kaggle.json

Note your:

username

key

📓 Databricks Notebook Execution

Create a new notebook in Databricks and execute the following cells sequentially.

1️⃣ Install Kaggle Dependency
!pip install kaggle

2️⃣ Configure Kaggle Credentials
import os

os.environ["KAGGLE_USERNAME"] = "your_username"
os.environ["KAGGLE_KEY"] = "your_key"

print("Kaggle credentials configured!")

3️⃣ Create Database Schema
spark.sql("""
CREATE SCHEMA IF NOT EXISTS workspace.ecommerce
""")

4️⃣ Create Volume for Data Storage
spark.sql("""
CREATE VOLUME IF NOT EXISTS workspace.ecommerce.ecommerce_data
""")

5️⃣ Download Dataset from Kaggle
cd /Volumes/workspace/ecommerce/ecommerce_data
kaggle datasets download -d mkechinov/ecommerce-behavior-data-from-multi-category-store

6️⃣ Extract Dataset Files
cd /Volumes/workspace/ecommerce/ecommerce_data
unzip -o ecommerce-behavior-data-from-multi-category-store.zip
ls -lh

7️⃣ Remove ZIP File
cd /Volumes/workspace/ecommerce/ecommerce_data
rm -f ecommerce-behavior-data-from-multi-category-store.zip
ls -lh

8️⃣ Restart Python Environment
%restart_python

📊 Loading Data into Spark
9️⃣ Load November 2019 Data
df_n = spark.read.csv(
    "/Volumes/workspace/ecommerce/ecommerce_data/2019-Nov.csv"
)

🔟 Load October 2019 Data
df = spark.read.csv(
    "/Volumes/workspace/ecommerce/ecommerce_data/2019-Oct.csv"
)

1️⃣1️⃣ Dataset Statistics & Schema
print(f"October 2019 - Total Events: {df.count():,}")
print("\n" + "="*60)
print("SCHEMA:")
print("="*60)
df.printSchema()

1️⃣2️⃣ Sample Data Preview
print("\n" + "="*60)
print("SAMPLE DATA (First 5 rows):")
print("="*60)
df.show(5, truncate=False)

🎯 Outcome of Day 0

By completing Day 0:

✅ Databricks environment is fully set up

✅ Kaggle dataset is stored in Databricks Volumes

✅ Large CSV files are successfully loaded into Spark

✅ Dataset is ready for transformations, SQL, and Delta Lake usage