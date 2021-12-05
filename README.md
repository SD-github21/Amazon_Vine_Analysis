# Amazon Vine Analysis
The purpose of the Amazon Vine analysis was to analyze Amazon reviews on videos and DVDs that were written by members of the Amazon Vine program who are paid for their reviews. First, an ETL process was conducted to extract an Amazon dataset, transform the data, connect to an AWS RDS instance, and load the transformed data into pgAmin for storage in a SQL database. Subsequently, an analysis was conducted to determine whether there was evidence of any bias towards favorable reviews from Amazon Vine program members. The report below details the results of the this second analysis investigating the presence of positivity bias for Amazon Vine program members (paid members). 

## Resources
- Data Sources: https://s3.amazonaws.com/amazon-reviews-pds/tsv/amazon_reviews_us_Video_DVD_v1_00.tsv.gz
- Software: Spark-3.0.3, Postgresql, pgAdmin4, Google Colab, PySpark, AWS RDS

## Results

Below are the important metrics calculated through this analysis in order to determine if there was evidence of any bias towards favorable reviews from Amazon Vine program members:

-	The total number of non-Vine unpaid reviews (n = 151,400) and the total number of Vine paid reviews (n = 49)

	![image](https://user-images.githubusercontent.com/85533099/144763924-02020fbf-0d70-431c-85b8-42dd8e2f184a.png)

-	The number of non-Vine unpaid five-star reviews (n = 78,061) and the total number of Vine paid five-star reviews (n = 9)

	![image](https://user-images.githubusercontent.com/85533099/144763954-84076ef9-0165-49ea-ae56-15d96795c5e0.png)

-	The percentage of non-Vine unpaid reviews that were five-star reviews (51.56%) and the percentage of non-Vine unpaid reviews that were five-star reviews (18.37%)

	![image](https://user-images.githubusercontent.com/85533099/144763980-892d9c11-ad5d-4560-93de-d8c89b8fc94d.png)

## Summary 

As outlined above, the percentage of unpaid non-Vine reviews that were five-star reviews was 51.56%, whereas the paid Vine reviews that were five-star reviews was 18.37%. These results suggest that there does not appear to be a positivity bias for the Vine reviews that are paid due to the relatively smaller percentage of five-star reviews for Amazon Vine program members. In fact, it appears that the Vine reviewers may have been particularly discerning and approached their reviews with a critical eye given the low percentage of five-star reviews. 

One additional analysis that could be performed with the data set to further examine whether there was positivity bias for the Vine reviews would be to filter the dataset to only include verified purchases and to run the analysis again to determine the percentage of five-star reviews within the non-Vine and Vine total reviews. 
  - By only including those reviews where customers were verified to have purchased the Video/DVD products from Amazon and not at an unusually large discount, this could help to curtail a positivity bias of five-star reviews and ensure that the reviews included in the final analysis are based upon typical purchases from Amazon. 
  - Furthermore, only examining reviews written on verified purchases could also help to weed out any errant reviews that might have been written by individuals who wanted to intentionally drive up the favorability of certain products by adding numerous five-star reviews. 
