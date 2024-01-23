# Data analysis and visualization with SQL and powerBI

## Sales Insights

**Introduction**

![](intro.png)

Altiq is a hardware that supplies computer hardware and periphirals to different clients across India. They have their head office in Delhi and other regional offices in different parts of India.

**Problem Statement**

With the market growing dynamically, the sales director is faced with a number of challenges:
1. There is an issue with understanding the reports from regional managers since they are bulky excel files
2. He wants to have a clear insight on how products are performing in different regions
3. He wants to see the trajectory of the business over the years
4. He He also wants to gain insights on who are his top and bottom clients

With this information he is certain his decisions will be more data driven.

**SQL Data Exploration**
Our schema named sales has 5 tables customers, date, markets, products and transactions



![](customers_table). 



When check our customers table, we have 38 records. From the dates table it appears the data ranges from 2017 - 2020. From the products table we can observe that there are 279 codes and 2 types of products (Own Brand and Distribution). Additionally we have a null record which could potentially affect our analysis. For market table, the company has spread accross 4 zones in 16 different mmarkets.
