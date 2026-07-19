# Home_Sales
can use Home_Sales/Home_Sales.ipynb/Home_Sales_google_colab.ipynb for code in Google Colab


can use Home_Sales.ipynb for code in Google Colab

Here is a clean, professional, and scannable `README.md` tailored for your GitHub repository. It clearly presents the purpose of the project, the workflow, and instructions for running the code in Google Colab.

---

# Home Sales Data Analysis

An analysis of housing market data utilizing **Apache Spark (PySpark)** and **SparkSQL** to determine key metrics surrounding home sales. This project focuses on processing large datasets, leveraging Spark's caching capabilities, and optimizing query performance through data partitioning.

---

## Project Overview

The objective of this analysis is to answer critical real estate questions by querying a dataset of historical home sales. The workflow demonstrates data ingestion, building temporary Spark SQL views, performance optimization via caching, and parallel processing via Parquet file formatting.

### Key Questions Answered

* What is the average price for a four-bedroom house for each year it was built?
* What is the average price of a home for each year it was built that has three bedrooms and three bathrooms?
* What is the average price of a home for each year it was built that has three bedrooms, three bathrooms, two floors, and is greater than or equal to 2,000 square feet?
* What is the average price of a home per "view" rating where the average home price is greater than or equal to $350,000? (Including a runtime comparison between uncached, cached, and partitioned data).

---

## File Structure

* `Home_Sales.ipynb`: Main Jupyter notebook containing the PySpark code.
* `Home_Sales_google_colab.ipynb`: Optimized notebook variant specifically configured for Google Colab environments.

---

## Technical Stack & Features

* **PySpark & SparkSQL**: For distributed data processing and relational querying.
* **Data Caching**: Utilizing `spark.catalog.cacheTable` to store temporary views in memory, significantly reducing query runtimes for repetitive analysis.
* **Parquet Partitioning**: Partitioning the dataset by the `date_built` field to optimize storage layout and speed up targeted queries.

---

## Getting Started

You can run this analysis directly in **Google Colab**, which provides pre-configured cloud environments ideal for running Spark sessions without local installation friction.

### Running in Google Colab

1. **Upload the Notebook**:
Open [Google Colab](https://colab.research.google.com/) and upload either `Home_Sales.ipynb` or `Home_Sales_google_colab.ipynb`.
2. **Install Dependencies**:
The initial cells of the notebook are configured to automatically install the required Java development kit, Apache Spark, and `findspark` libraries directly into the Colab instance:
```bash
!apt-get install openjdk-8-jdk-headless -qq > /dev/null
!wget -q http://www.apache.org/dist/spark/spark-3.x.x/spark-3.x.x-bin-hadoop3.tgz
!tar xf spark-3.x.x-bin-hadoop3.tgz
!pip install -q findspark

```


3. **Execute the Code**:
Run the cells sequentially (`Runtime > Run all`) to initialize the Spark Session, ingest the home sales data, and execute the analytical queries.

---

## Performance Metrics & Summary

The final section of the analysis evaluates runtime differences across three environments:

1. **Uncached Temporary Table**: Standard query processing time.
2. **Cached Temporary Table**: Demonstrates a runtime drop due to in-memory evaluation.
3. **Partitioned Parquet Data**: Highlights how filtering performance scales when Spark only scans relevant data partitions.
