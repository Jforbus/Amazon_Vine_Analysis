# Amazon_Vine_Analysis

## Project Overview
Analyzing Amazon review data for products in the *Watches* category to determine if a correlation exists between positive reviews and reviews in the paid Vine program.
Data is collected from S3 and processed using Spark. The total number of Vine and Non-Vine reviews are counted, as well as the number of 5 Star reviews in each category. From this the percentage of 5 Star reviews in each category is calculated to determine which category has a greater percentage of 5 Star reviews.

### Resources
Data Source: https://s3.amazonaws.com/amazon-reviews-pds/tsv/amazon_reviews_us_Watches_v1_00.tsv.gz
Software: Google Colaboratory, Spark 3.3.1, pgAdmin 4, VScode 1.73.1

## Results
The data is loaded into a Google Colab notebook and used to generate a Dataframe with pyspark. This dataframe is then filtered multiple times to contain only reviews with 20 or more total votes, and at least 50% helpful votes. These reviews are then split into two seperate dataframes, one for those in the Vine Program, and another for Non-Vine program reviews.
![Y_script](https://github.com/Jforbus/Amazon_Vine_Analysis/blob/main/Resources/Y_script.png)
![Y_Dataframe](https://github.com/Jforbus/Amazon_Vine_Analysis/blob/main/Resources/Y_Dataframe.png)

![N_script](https://github.com/Jforbus/Amazon_Vine_Analysis/blob/main/Resources/N_script.png)
![N_Dataframe](https://github.com/Jforbus/Amazon_Vine_Analysis/blob/main/Resources/N_Dataframe.png)

These dataframes are used to calculate the vote counts for each group.

Vine Program Reviews:
- Total Reviews: 47
- 5 Star Reviews: 15
- Percentage of total: 32%

![Vine_counts](https://github.com/Jforbus/Amazon_Vine_Analysis/blob/main/Resources/Vine_counts.png)

Non-Vine Program Reviews:
- Total Reviews: 9337
- 5 Star Reviews: 4496
- Percentage of total: 48.2%

![Non_vine_counts](https://github.com/Jforbus/Amazon_Vine_Analysis/blob/main/Resources/Non_vine_counts.png)

## Summary
The analysis shows that a lower percentage of 5 star reviews exists in the Vine Program by what appears to be a significant amount. 48.2% of the reviews outside the Vine Program are 5 star reviews. Only 32% of reviews in the Vine Program are 5 star reviews. From this data it does not appear that there is a positivity bias for reviews in the Vine Program. 

However, Vine Program reviews account for only 47 reviews in the *Watches* category, compared to 9337 reviews not in the program. The small data set present here for the Vine Program may be hindering the analysis. 

An additional analysis could help give further insight. 4 Star reviews are also considered positive reviews. Conducting a count and calculating the percentage of 4 Star reviews in each category as done for 5 Star reviews would add relevant data and potentially support the prior findings.  