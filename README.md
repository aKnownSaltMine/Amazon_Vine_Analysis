# Amazon_Vine_Analysis
## Overview
The Amazon Vine program is allows Sellers on the Amazon Marketplace to send products to members of the program in order for them to review them. The company pays a fee in order to access this program, and those who receive the product from the seller are required to review it. 

This is seen as a good way for sellers to get their products into the hands of verified purchasers and ensure a review of their product, something that overall can place their product higher on search algorithm results, thus bringing in more sales. However, there is the chance of natural bias. Because the people reviewing the products are not necessarily buying the product and are getting paid for the reviews, there is a possibility that their results will be positively biased. In order to check this, we have examined Amazon Video Game review Dataset in order to examine the scores given in reviews against whether or not they were in the vine program. 

In order to do this, we used Spark 3.2.1 in order to load in the dataset, create the different dataframes and export them to PostgreSQL. We then were able to perform further analysis of the data using PySpark for statistical examinations of the review set. 

## Results
### Dataframes
#### Helpful Reviews Dataframe (top 20)
![filtered_help_df](https://github.com/aKnownSaltMine/Amazon_Vine_Analysis/blob/main/Results/filtered_help_df.png)

#### Paid Review Dataframe (top 20)
![paid_df](https://github.com/aKnownSaltMine/Amazon_Vine_Analysis/blob/main/Results/paid_df.png)

#### Unpaid Review Dataframe (top 20)
![upaid_df](https://github.com/aKnownSaltMine/Amazon_Vine_Analysis/blob/main/Results/unpaid_df.png)

### Statistics
* When examining the Amazon Video Game Review set data, out of 40,565 total reviews that were considered helpful, only 94 of them were actually members of the vine program leaving the other 40,471 reviews as non vine program reviews. This means that only 0.23% of the total helpful reviews are actually coming out of the vine program. So out of the total amount of reviews, the vine program represent a very small amount of the total reviews that are present in the dataset. 

* However out of the total reviews, 15,711 were given 5 stars. 15,663 of these votes were unpaid leaving the other 48 to be a part of the vine program. 

* This means that out of the total reviews, the dataset had 38.73% of the total reviews as 5 stars, but when filtered out the paid reviews, the rate of five stars goes to 38.70%. But overall, the rate of paid reviews being at 5 stars is over half with 51.06% of the reviews being 5 stars.

## Summary

When examining the Video Game Review Dataset, it becomes clear that there is definitely a positivity bias when looking at the vine program. Over half of all of the vine program reviews were 5 stars with 76% of the reviews make up 4 stars or higher. This is contrasted against the fact that the unpaid reviews maintain a 38% for 5 star reviews and 55.35% for reviews 4 stars or higher. However, it must be taken into consideration that the vine program makes up for such a small amount of the total reviews that is hardly has an effect on the total positivity ratings when taken out or kept in. 

One thing to look into doing moving forward to further the analysis would be to group the review sets by product ids and to examine which products tend to have more vine program reviews and less. Then with that understanding, examine the positivity scores of the vine program in order to see the possibility of real world swaying of reviews by utilizing the vine program.
