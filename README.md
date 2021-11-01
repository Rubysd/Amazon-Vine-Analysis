# Amazon-Vine-Analysis

![image](https://user-images.githubusercontent.com/86340630/139617865-78b0abd9-4ce0-44f0-befa-63ac736b8e5b.png)

## Overview of Project

Since your work with Jennifer on the SellBy project was so successful, you’ve been tasked with another, larger project: analyzing Amazon reviews written by members of the paid Amazon Vine program. The Amazon Vine program is a service that allows manufacturers and publishers to receive reviews for their products. Companies like SellBy pay a small fee to Amazon and provide products to Amazon Vine members, who are then required to publish a review.

In this project, you’ll have access to approximately 50 datasets. Each one contains reviews of a specific product, from clothing apparel to wireless products. You’ll need to pick one of these datasets and use PySpark to perform the ETL process to extract the dataset, transform the data, connect to an AWS RDS instance, and load the transformed data into pgAdmin. Next, you’ll use PySpark, Pandas, or SQL to determine if there is any bias toward favorable reviews from Vine members in your dataset. Then, you’ll write a summary of the analysis for Jennifer to submit to the SellBy stakeholders.

# Deliverables:

This new assignment consists of two technical analysis deliverables and a written report.

1. Deliverable 1: Perform ETL on Amazon Product Reviews
2. Deliverable 2: Determine Bias of Vine Reviews
3. Deliverable 3: A Written Report on the Analysis README.md

# Deliverable 1:

Perform ETL on Amazon Product Review 

## Deliverable Requirements:

Using the cloud ETL process, you’ll create an AWS RDS database with tables in pgAdmin, pick a dataset from the Amazon Review datasets, and extract the dataset into a DataFrame. You'll transform the DataFrame into four separate DataFrames that match the table schema in pgAdmin. Then, you'll upload the transformed data into the appropriate tables and run queries in pgAdmin to confirm that the data has been uploaded.

To Deliver.

Follow the instructions below:

1. From the following Amazon Review datasets, pick a dataset that you would like to analyze. All the datasets have the same schemata, as shown in this image:

![image](https://user-images.githubusercontent.com/86340630/139611608-c7df8ebd-923e-472f-85af-19678735ce9a.png)

2. Create a new database with Amazon RDS just as you did in this module.

3. In pgAdmin, create a new database in your Amazon RDS server that you just create.

4. Download the challenge_schema.sql file to your computer.

5. In pgAdmin, run a new query to create the tables for your new database using the code from the challenge_schema.sql file.

° After you run the query, you should have the following four tables in your database: customers_table, products_table, review_id_table, and vine_table.

6. Download the Amazon_Reviews_ETL_starter_code.ipynb file, then upload the file as a Google Colab Notebook, and rename it Amazon_Reviews_ETL.

NOTE

If you try to open the Amazon_Reviews_ETL_starter_code.ipynb with jupyter notebook it will give you an error.

7. First extract one of the review datasets, then create a new DataFrame.

8. Next, follow the steps below to transform the dataset into four DataFrames that will match the schema in the pgAdmin tables:

NOTE

Some datasets have a large number of rows, which will affect the time it takes to complete the following steps.

The customers_table DataFrame To create the customers_table, use the code in the Amazon_Reviews_ETL_starter_code.ipynb file and follow the steps below to aggregate the reviews by customer_id.

* Use the groupby() function on the customer_id column of the DataFrame you created in Step 6.
* Count all the customer ids using the agg() function by chaining it to the groupby() function. After you use this function, a new column will be created, count(customer_id).
* Rename the count(customer_id) column using the withColumnRenamed() function so it matches the schema for the customers_table in pgAdmin.
* The final customers_table DataFrame should look like this:

![image](https://user-images.githubusercontent.com/86340630/139611936-90db10b3-47b3-41ca-8d34-e0e9a4729bd9.png)

The products_table DataFrame To create the products_table, use the select() function to select the product_id and product_title, then drop duplicates with the drop_duplicates() function to retrieve only unique product_ids. Refer to the code snippet provided in the Amazon_Reviews_ETL_starter_code.ipynb file for assistance.

The final products_table DataFrame should look like this:

![image](https://user-images.githubusercontent.com/86340630/139612014-ce868646-e330-4acd-a27c-427180cc8681.png)

The review_id_table DataFrame To create the review_id_table, use the select() function to select the columns that are in the review_id_table in pgAdmin, and convert the review_date column to a date using the code snippet provided in the Amazon_Reviews_ETL_starter_code.ipynb file.

The final review_id_table DataFrame should look like this:

![image](https://user-images.githubusercontent.com/86340630/139612043-4fd1d36e-7259-4138-9614-2993cc0fbd54.png)

The vine_table DataFrame To create the vine_table, use the select() function to select only the columns that are in the vine_table in pgAdmin.

The final vine_table DataFrame should look like this:

![image](https://user-images.githubusercontent.com/86340630/139612085-9e49a4b2-e65f-446d-868f-7455ce753283.png)

Load the DataFrames into pgAdmin

Make the connection to your AWS RDS instance.
Load the DataFrames that correspond to tables in pgAdmin.
In pgAdmin, run a query to check that the tables have been populated.
IMPORTANT

Before uploading anything to GitHub be sure to remove all sensitive information such as passwords and connection strings. If you have accidentally done so already see this link (Links to an external site.) for more information.

When you’re done, export your Amazon_Reviews_ETL Google Colab Notebook as an ipynb file, and save it to your Amazon_Vine_Analysis GitHub repository.

NOTE Uploading each DataFrame can take up to 10 minutes or longer, so it’s a good idea to double-check your work before uploading. If you have problems uploading your work, you may have to shut down the pgAdmin server and restart. Alternatively, you may have to delete the tables and create them again, then re-run your Amazon_Reviews_ETL Google Colab Notebook.

IMPORTANT Be sure that you don’t leave your RDS instance up too long. Try to get all your work for Deliverable 1 done in one sitting, then shut down your instance. Please consult the AWS clean-up videos for more information about shutting down your RDS instance. You will not be graded on anything contained strictly in your RDS, so be sure to shut it down.

## Deliverable 1 Requirements
You will earn a perfect score for Deliverable 1 by completing all requirements below:

The Amazon_Reviews_ETL.ipynb file does the following:
An Amazon Review dataset is extracted as a DataFrame
The extracted dataset is transformed into four DataFrames with the correct columns
All four DataFrames are loaded into their respective tables in pgAdmin

# DELIVERABLE RESULTS:

# Extract

Read the url form Amazon S3 drive and extract the data to a DataFrame

![Captura de pantalla (957)](https://user-images.githubusercontent.com/86340630/139612620-a871d439-d7f1-4889-9af3-e1ddf0db9d07.png)

# Transform

Transform the data to a smallest DataFrames

![Captura de pantalla (959)](https://user-images.githubusercontent.com/86340630/139613178-6c4de4c6-a133-42cf-a6e4-e71b9378ca48.png)

# Load

Load the data to a RDS in Amazon Web Service

![Captura de pantalla (961)](https://user-images.githubusercontent.com/86340630/139613391-008e4ceb-5a2a-4c51-985a-28d4202d096e.png)

Results: Using bulleted lists and images of DataFrames as support, address the following questions:

# Resume table

![image](https://user-images.githubusercontent.com/86340630/139613572-6585a6a6-2005-468a-ae79-645cf7bef86b.png)

1. How many Vine reviews and non-Vine reviews were there?

### Vine reviews : 266
### non/Vine reviews : 38,829

![Captura de pantalla (963)](https://user-images.githubusercontent.com/86340630/139615013-0d623e9a-fd24-4d9c-8c55-30561382e117.png)
![Captura de pantalla (965)](https://user-images.githubusercontent.com/86340630/139615211-5c68ca73-bdc8-4d48-9dfa-192c95047f2f.png)


2. How many Vine reviews were 5 stars? How many non-Vine reviews were 5 stars?

## Vine reviews : 125
## non/Vine reviews : 18,246

What percentage of Vine reviews were 5 stars? What percentage of non-Vine reviews were 5 stars?

Vine reviews : 46.99%
non/Vine reviews : 46.99%

![Captura de pantalla (967)](https://user-images.githubusercontent.com/86340630/139615930-388ea7c8-f03d-4666-8041-501d62db03ab.png)

Summary: In your summary, state if there is any positivity bias for reviews in the Vine program. Use the results of your analysis to support your statement. Then, provide one additional analysis that you could do with the dataset to support your statement.

# SUMMARY

There appears to be no positivity bias for reviews on the Vine show, especially for votes paid with verified purchase. 
It could be a lot 51.06%, but at the same time, that considers a low voter count compared to unpaid members. 
This last filter, which was used to see the difference as precisely as possible, is one of many that could be used to give more meaning to the data.

# RECOMMENDATIONS:

Below some recommendations to follow:
The Amazon Vine Analysis provide a favorable dataset on the 5-star rating.
In addition, we found that much data isn't Vine reviews over specific products, that we could minimize the resluts and create a different dataset on just Vine products.








