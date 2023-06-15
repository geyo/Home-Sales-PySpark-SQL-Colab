# Home Sales Analysis Using PySpark SQL

**Programming Languages/Tools Used:** PySpark SQL, Jupyter Notebook, Google Colab

## Purpose

The purpose of this project is to determine key metrics about home sales data, and to use Spark to create temporary views, parition the data, cache and uncache a tempoerary table. 

## Process

I started the project in Jupyter notebooks using the Google Colab cloud. I imported Sparkfiles from PySpark to load the home sales csv data stored in the cloud. Then, I created a temporary table, and answered the questions about the data using SparkSQL. The following is a snippet of questions answered:

- What is the average price for a four-bedroom house sold for each year? 

```python
spark.sql("SELECT date_built, ROUND(AVG(price),2) AS average_price FROM home_sales WHERE bedrooms==4 GROUP BY date_built").show()
```
![image](https://github.com/geyo/Home-Sales-SparkSQL-Colab/assets/8386502/6187ab84-0b7f-43d3-8fb5-54754ef6a90b)


- What is the average price of a home for each year it was built that has three bedrooms and three bathrooms? 

```python
spark.sql("SELECT date_built, ROUND(AVG(price),2) AS average_price FROM home_sales WHERE bedrooms==3 AND bathrooms==3 GROUP BY date_built").show()
```
![image](https://github.com/geyo/Home-Sales-SparkSQL-Colab/assets/8386502/aaf35887-9bc7-4f1b-8b87-bc2ac4915272)

