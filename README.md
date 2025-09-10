# BIG-DATA-ANALYSIS
*COMPANY* - CODTECH IT SOLUTION

*NAME* - SOHAM MAHAJAN

*INTERNID* - CT04DY2129

*DOMAIN* - DATA ANALYST

*DURATION* - 4 WEEKS

*MENTOR* -  NEELA SANTOSH

This project was developed as part of my internship assignment to perform analysis on a large dataset using tools like PySpark to demonstrate scalability. 
The main objective was not just to process a dataset but to show how distributed data processing frameworks like PySpark can scale when working with increasingly large datasets and different partitioning strategies.

Big data technologies such as PySpark are widely used in the industry for analyzing and processing datasets that cannot fit into the memory of a single machine. In this task, I created a synthetic e-commerce dataset with millions of simulated transactions and then applied PySpark to perform aggregations such as finding top products by sales. Most importantly, I measured runtime performance under different dataset sizes and partition counts, which allowed me to demonstrate how scalability works in real-world scenarios.

Since I did not have access to a real big data source, I generated a synthetic dataset that resembles e-commerce transactions. The dataset includes the following fields:

"*order_id*" – Unique identifier for each transaction.

"*timestamp (ts)*" – When the transaction occurred.

"*user_id*" – Customer identifier.

"*product_id*" – Identifier for purchased product.

"*price*" – Unit price of the product.

"*quantity*" – Number of items purchased.

"*category*"– Product category (electronics, clothing, sports, etc.).

"*country*" – Country where the transaction took place.

"*device*" – Device used by the customer (mobile, desktop, tablet).

"*rating*" – Product rating given by the customer.

The dataset was generated in chunks to simulate how real-world large datasets are often stored in multiple files. I used NumPy and Pandas to generate realistic data distributions (e.g., higher probability of purchases from certain countries or higher frequency of mobile users).
I created datasets of different sizes: 50,000 rows, 100,000 rows, and 200,000 rows. These varying sizes were later used to test scalability.

*DATA PROCESSING WITH PYSPARK*

For the analysis, I used PySpark. Spark is known for its ability to process huge datasets in a distributed manner, both on clusters and on a single machine. In my case, I ran Spark in local mode with multiple cores to simulate distributed processing.
The key processing steps were:

"*Load CSV Data*" – Using Spark’s CSV reader with a predefined schema for efficiency.

"*Data Cleaning & Feature Engineering*" – Converted timestamps, extracted order date, and computed a new column total_sales = price * quantity.

"*Partitioning & Caching*" – Repartitioned data by country with varying numbers of partitions (10, 50, 100) and cached the dataset to improve repeated queries.

"*Aggregation*" – Calculated top 10 products by total sales across the dataset.

"*Export Results*" – Saved results to CSV files inside an output directory.

*THE CORE* part of this project was the scalability test. I wanted to demonstrate how runtime changes as we scale data and adjust partitions. To do this, 

I Generated datasets of 50k, 100k, and 200k rows.

Ran the same aggregation task with 10, 50, and 100 partitions.

Measured the execution time for each combination.

For each run, I stored the runtime in a table (output/scalability_results.csv). Finally, I visualized the results using Matplotlib, plotting runtime against partitions for each dataset size.
The results clearly showed that:

Increasing dataset size increased runtime.

Increasing partitions reduced runtime up to a point, after which the benefit plateaued or even worsened due to shuffle overhead.

This validated the principle that parallelism helps scalability but must be tuned carefully.

*OUTPUT*

<img width="496" height="794" alt="Image" src="https://github.com/user-attachments/assets/61634915-19b4-40c8-b4a8-705c94e9984a" />
