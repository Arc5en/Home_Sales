# Home_Sales

Included in this repository are two different sets of code that functionally perform the same.

The first is the jupyter notebook that mainly utilizes the Spark module to efficiently perform SQL queries. It is highly recommended to upload the notebook onto Google colab to efficiently run all the cells. Most local computers may take a significant amount of time to run a single query, let alone all of them.

The second is the databricks cloud notebook that also utilizes the Spark module on the cloud and is able to perform the queries nearly on par with the jupyter notebook. It needs to be downloaded to access the notebook. While its performance is highly lauded, I was only able to utilize the Community Edition of Databricks, along with a few tweaks to the jupyter notebook code, to perform these queries. The Community Edition also comes with the limitation of having a two week free trial before you are prompted to pay for it. 

Here are the questions answered by both sets of code:

What is the average price for a four bedroom house sold in each year rounded to two decimal places?
+----+-------------+
|YEAR|AVERAGE_PRICE|
+----+-------------+
|2022|    296363.88|
|2021|    301819.44|
|2020|    298353.78|
|2019|    300263.70|


What is the average price of a home for each year the home was built that have 3 bedrooms and 3 bathrooms rounded to two decimal places?
+----------+-------------+
|YEAR_BUILT|AVERAGE_PRICE|
+----------+-------------+
|      2017|    292676.79|
|      2016|    290555.07|
|      2015|     288770.3|
|      2014|    290852.27|
|      2013|    295962.27|
|      2012|    293683.19|
|      2011|    291117.47|
|      2010|    292859.62|

What is the average price of a home for each year built that have 3 bedrooms, 3 bathrooms, with two floors,
and are greater than or equal to 2,000 square feet rounded to two decimal places?
+----------+-------------+
|YEAR_BUILT|AVERAGE_PRICE|
+----------+-------------+
|      2017|    280317.58|
|      2016|     293965.1|
|      2015|    297609.97|
|      2014|    298264.72|
|      2013|    303676.79|
|      2012|    307539.97|
|      2011|    276553.81|
|      2010|    285010.22|

What is the "view" rating for the average price of a home, rounded to two decimal places, where the homes are greater than
or equal to $350,000? Determine the run time for this query noncached, cached, and partitioned + parquet dataframe. (Only top 20 rows displayed)
+----+-------------+
|view|AVERAGE_PRICE|
+----+-------------+
|  99|   1061201.42|
|  98|   1053739.33|
|  97|   1129040.15|
|  96|   1017815.92|
|  95|    1054325.6|
|  94|    1033536.2|
|  93|   1026006.06|
|  92|    970402.55|
|  91|   1137372.73|
|  90|   1062654.16|
|  89|   1107839.15|
|  88|   1031719.35|
|  87|    1072285.2|
|  86|   1070444.25|
|  85|   1056336.74|
|  84|   1117233.13|
|  83|   1033965.93|
|  82|    1063498.0|
|  81|   1053472.79|
|  80|    991767.38|

~1.17s on Google Colab notebook uncached, ~0.48s on notebook cached, ~0.48s on notebook with the parquet DataFrame. Cached was slightly faster by ~ 0.003 seconds, a slim margin.

~1.71s on databricks uncached, ~0.61s on databricks cached, ~1.53s on databricks with the parquet DataFrame. Cached was noticeably faster by nearly a second. It is slower than the notebook but not by a significant margin. 

