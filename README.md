# Amazon Vine Analysis
## Overview of the Analysis
In this project, I took videogame product reviews to determine if there was a positive bias for paid Vine reviews. First, I imported the raw data from AWS S3 and imported that into my google collaboratory file. Using PySpark, I loaded the data into a DataFrame to better manipulate the data. I had created an RDS in AWS, which I linked to PGAdmin. I created blank tables that could then be filled in by data that I analyzed in PySpark. The original DataFrame was split into 4 more DataFrames: customers_df, products_df, review_id_df, and vine_df. I then wrote each DataFrame into the corresponding tables in postgreSQL. These tables will be useful for SellBy to have access to in the future, and it demonstrates the power of utilizing cloud-based data storage that can connect to postgreSQL and other databases.

Next, I took the raw data and filtered it down to a DataFrame where the products that had 20 reviews or more. I filtered it again to set up a DataFrame that had 50% or greater helpful reviews. I then created two DataFrames: one that had only paid vine votes, and one that had the unpaid votes. I then was able to get the total counts of total votes, 5 star votes, and the percentage of 5-star votes to total votes for each DataFrame. This helped me decide whether paid votes had a positive bias or not.
## Results
### Paid Votes/Reviews Analysis
![](https://github.com/mabuckjr/Amazon_Vine_Analysis/blob/main/Resources/paid_review_analysis.PNG)

There were only 94 paid votes from Vine. 48 of those were 5-star reviews, meaning that 51% of the votes were 5-stars. Even before I had conducted the analysis on the unpaid reviews, it seemed like a pretty high percent.
### Unpaid Votes/Reviews Analysis
![](https://github.com/mabuckjr/Amazon_Vine_Analysis/blob/main/Resources/unpaid_review_analysis.PNG)

By comparison, there were 40,471 total votes, with 15,663 of those being 5-star reviews. While 39% of reviews being 5-stars is still pretty high, it is much lower than the paid review percentage.
## Summary
Overall, I would argue that there is a positivity bias for the paid reviews for videogame products in the Vine program. With 51% of paid reviews being 5-stars and only 39% of unpaid reviews being 5-stars, there's a clear difference that could be explained by the Vine program. Having said that, there are far less paid reviews than there are unpaid reviews, so it may be hasty to assume this with the data we have. It would likely be better to accumulate more of this data over time to see if this trend persists. It's also important to not assume that this applies to all product reviews, as my study was only focused on videogame votes only.

To be  sure of whether there is a positivity bias or not, it would be a good idea to compare 4-star and 3-star ratings as well. The best way to do this would be to compare all reviews 3-stars or higher for both paid and unpaid votes. This would give more data, making the results even more clear of whether there is a positivity bias or not. If there is still a much higher percentage of positive paid votes than positive unpaid votes, than we'd be able to decide with more certainty if there is a positive bias or not.
