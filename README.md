# Data analysis and visualization with SQL and powerBI

## Sales Insights

### **Introduction**

![Alt Text](https://github.com/WinnieKiarago/Data_Analytics-/blob/main/Data%20Analysis%20-%20Sales%20Insights/intro.png)

Altiq is a hardware that supplies computer hardware and periphirals to different clients across India. They have their head office in Delhi and other regional offices in different parts of India.

### **Problem Statement**

With the market growing dynamically, the sales director is faced with a number of challenges:
1. There is an issue with understanding the reports from regional managers since they are bulky excel files
2. He wants to have a clear insight on how products are performing in different regions
3. He wants to see the trajectory of the business over the years
4. He He also wants to gain insights on who are his top and bottom clients

With this information he is certain his decisions will be more data driven.

### **SQL Data Exploration**

Our schema named sales has 5 tables customers, date, markets, products and transactions

![Alt Text](https://github.com/WinnieKiarago/Data_Analytics-/blob/main/Data%20Analysis%20-%20Sales%20Insights/sales_schema.JPG)

When check our customers table, we have 38 records.

![Alt Text](https://github.com/WinnieKiarago/Data_Analytics-/blob/main/Data%20Analysis%20-%20Sales%20Insights/customers_table.JPG)

From the dates table it appears the data was collected between 2017 and 2020.

![Alt Text](https://github.com/WinnieKiarago/Data_Analytics-/blob/main/Data%20Analysis%20-%20Sales%20Insights/years.JPG)


From the products table we can observe that there are 279 codes and 2 types of products (Own Brand and Distribution).

![Alt Text](https://github.com/WinnieKiarago/Data_Analytics-/blob/main/Data%20Analysis%20-%20Sales%20Insights/products.png)

Additionally we have a null record which could potentially affect our analysis. 


For market table, we see that the company is spread accross 4 zones in 16 different markets.

![Alt Text](https://github.com/WinnieKiarago/Data_Analytics-/blob/main/Data%20Analysis%20-%20Sales%20Insights/market_zones.JPG)

![Alt Text](https://github.com/WinnieKiarago/Data_Analytics-/blob/main/Data%20Analysis%20-%20Sales%20Insights/markets.PNG)

Let's look at the total revenue collected as well as the sales made during this period respectively

![Alt Text](https://github.com/WinnieKiarago/Data_Analytics-/blob/main/Data%20Analysis%20-%20Sales%20Insights/revenue.PNG)

Revenue Collected between 2017 and 2020 /|\



![Alt Text](https://github.com/WinnieKiarago/Data_Analytics-/blob/main/Data%20Analysis%20-%20Sales%20Insights/total_sales.PNG)

Total sales made between 2017 and 2020 /|\

From the currency column we see that payment are made in Indian Rupees(INR) or US Dollars(USD).


![Alt Text](https://github.com/WinnieKiarago/Data_Analytics-/blob/main/Data%20Analysis%20-%20Sales%20Insights/currency.PNG)

### **Analysis with Power BI**


The model is a star schema consisting of 5 tables whereby one of the tables is a fact table and the others are dimensional tables.

![Alt Text](https://github.com/WinnieKiarago/Data_Analytics-/blob/main/Data%20Analysis%20-%20Sales%20Insights/adjusted_topology.png)

