# Amazon Vine Analysis
## Overview of the Analysis
In this project, I took videogame product reviews to determine if there was a positive bias for paid Vine reviews. First, I imported the raw data from AWS S3 and imported that into my google collaboratory file. Using PySpark, I loaded the data into a DataFrame to better manipulate the data. I had created an RDS in AWS, which I linked to PGAdmin. I created blank tables that could then be filled in by data that I analyzed in PySpark. The original DataFrame was split into 4 more DataFrames: customers_df, products_df, review_id_df, and vine_df. I then wrote each DataFrame into the corresponding tables in postgreSQL. These tables will be useful for SellBy to have access to in the future, and it demonstrates the power of utilizing cloud-based data storage that can connect to postgreSQL and other databases.
Next, I took the raw data and filtered it down to a DataFrame where the products that had 20 reviews or more. I filtered it again to set up a DataFrame that had 50% or greater helpful reviews. I then created two DataFrames: one that had only paid vine votes, and one that had the unpaid votes. I then was able to get the total counts of total votes, 5 star votes, and the percentage of 5-star votes to total votes for each DataFrame. This helped me decide whether paid votes had a positive bias or not.
## Analysis
