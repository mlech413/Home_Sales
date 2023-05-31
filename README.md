# Home_Sales
## Used SparkSQL to determine key metrics about home sales data, then used Spark to create temporary views, partition the data, cache and uncache a temporary table, and verify that the table has been uncached.

Input file in AWS S3 bucket was imported: "https://2u-data-curriculum-team.s3.amazonaws.com/dataviz-classroom/v1.2/22-big-data/home_sales_revised.csv" into Jupyter Notebook "home_sales.ipynb" and run in Google Colabaratory.

SQL used to determine:
* The average price for a four-bedroom house sold for each year, rounded to two decimal places.
* The average price of a home for each year it was built that has three bedrooms and three bathrooms.
* The average price of a home for each year that has three bedrooms, three bathrooms, two floors, and is gat least 2,000 square feet.
* The "view" rating for homes costing more than or equal to $350,000.

Three methods were timed and compared for the final query ("view" rating query for homes $350k+):
* 0.3489 seconds: SparkSQL temporary table.
* 0.2268 seconds: Cached temporary table.
* 0.2456 seconds: Formatted parquet data by partitioning the "date_built" field.