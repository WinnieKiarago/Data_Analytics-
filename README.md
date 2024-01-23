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

Additionally we have a null record which could potentially affect our analysis if altered. 


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


The model is a star schema consisting of 5 tables whereby one of the tables is a fact table and the rest are dimensional tables.

  Default topology
:-----------------------------:

![Alt Text](https://github.com/WinnieKiarago/Data_Analytics-/blob/main/Data%20Analysis%20-%20Sales%20Insights/original%20topology.png)

  Adjusted topology
:-----------------------------: 
![Alt Text](https://github.com/WinnieKiarago/Data_Analytics-/blob/main/Data%20Analysis%20-%20Sales%20Insights/adjusted_topology.png)

### **ETL**
The markets table has some missing zones. I'll filter out the empty zones.

  Original Markets Table Data 
:----------------------------: 

  ![Alt Text](https://github.com/WinnieKiarago/Data_Analytics-/blob/main/Data%20Analysis%20-%20Sales%20Insights/markets_table.jpg)

fx= Table.SelectRows(sales_markets, each true)

  Filtered  Markets Table Data
:-----------------------------:

  ![Alt Text](https://github.com/WinnieKiarago/Data_Analytics-/blob/main/Data%20Analysis%20-%20Sales%20Insights/marketzoneafterETL.png)

fx= Table.SelectRows(sales_markets, each ([zone] <> ""))

On the transactions table, we see there are some zero and negative values. I'll filter that out. We also see that the currency is in INR and USD. I will convert USD to INR since that is the currency used most.

  Original Transactions Table Data
:----------------------------------:

   ![Alt Text](https://github.com/WinnieKiarago/Data_Analytics-/blob/main/Data%20Analysis%20-%20Sales%20Insights/transactions_unfiltered.png)

   Transformed Transactions Table Data
:---------------------------------------:

   ![Alt Text](https://github.com/WinnieKiarago/Data_Analytics-/blob/main/Data%20Analysis%20-%20Sales%20Insights/transactionsafterETL.png)

From the above table, I created a column **'Normalize_sales_amount'** which I used to convert USD to INR using the exxhange rate

### **Visualization**

I will first create the base measures table which will help us create other elements on our dashboard. In this case I will use revenue and sales quantity. I'll then add different elements such as year, zones, markets etc in order to give clear insights of how the company is performing.

This is the final dashboard I created.

![Alt Text](https://github.com/WinnieKiarago/Data_Analytics-/blob/main/Data%20Analysis%20-%20Sales%20Insights/final_dashboard.png)

lets see how the products are performing in different regions

   ### The 'blank product'

   2017
:--------:

![Alt Text](https://github.com/WinnieKiarago/Data_Analytics-/blob/main/Data%20Analysis%20-%20Sales%20Insights/blank2017.png)

Majority of the revenue was collected in the North zone which amounted to 38.88% while the least revenue was collected in the South Zone which amounted to 0.46%. The month of November recorded the highest sales as well as revenue.

   2018
 :--------:

![Alt Text](https://github.com/WinnieKiarago/Data_Analytics-/blob/main/Data%20Analysis%20-%20Sales%20Insights/blank2018.png)

The highest amount of sales made and revenue collected was in the month of August. There was an increase in revenue from 48.90M to 200.61M with the South zone recording an increase of 0.5% increase in sales compared to the previous year.

   2019
 :--------:

![Alt Text](https://github.com/WinnieKiarago/Data_Analytics-/blob/main/Data%20Analysis%20-%20Sales%20Insights/blank2019.png)

There was a significant drop in revenue of 46M with July recording the highest revenue and August the highest sales. All zone had dropped in sales as well as revenue collected.

   2020
 :--------:

![Alt Text](https://github.com/WinnieKiarago/Data_Analytics-/blob/main/Data%20Analysis%20-%20Sales%20Insights/blank2020.png)

This year recorded the lowest amount of revenue and sales compared to the previous months. The North Zone still recorded the largest amount of sales and revenue.


  ### Own Brand

   2017
:--------:

![Alt Text](https://github.com/WinnieKiarago/Data_Analytics-/blob/main/Data%20Analysis%20-%20Sales%20Insights/own2017.png)


   2018
 :--------:

![Alt Text](https://github.com/WinnieKiarago/Data_Analytics-/blob/main/Data%20Analysis%20-%20Sales%20Insights/own2018.png)

   2019
 :--------:

![Alt Text](https://github.com/WinnieKiarago/Data_Analytics-/blob/main/Data%20Analysis%20-%20Sales%20Insights/own2019.png)

   2020
 :--------:

![Alt Text](https://github.com/WinnieKiarago/Data_Analytics-/blob/main/Data%20Analysis%20-%20Sales%20Insights/own2020.png)


  ### Distribution

   2017
:--------:

![Alt Text](https://github.com/WinnieKiarago/Data_Analytics-/blob/main/Data%20Analysis%20-%20Sales%20Insights/Distribution2017.png)


   2018
 :--------:

![Alt Text](https://github.com/WinnieKiarago/Data_Analytics-/blob/main/Data%20Analysis%20-%20Sales%20Insights/Distribution2018.png)


   2019
 :--------:

![Alt Text](https://github.com/WinnieKiarago/Data_Analytics-/blob/main/Data%20Analysis%20-%20Sales%20Insights/Distribution2019.png)

   2020
 :--------:

 ![Alt Text](https://github.com/WinnieKiarago/Data_Analytics-/blob/main/Data%20Analysis%20-%20Sales%20Insights/Distribution2020.png)

### Observations

1. Based on these visuals, the North zone seem to be winning all through the years. I has recorded the highest sales as well as revenue. The Cental zone has remained the middle ground while the South zone constantly recording the least sales and revenue.
2. The business started with a total revenue of 92.88M in 2017.

  2017
:--------:
  
  ![Alt Text](https://github.com/WinnieKiarago/Data_Analytics-/blob/main/Data%20Analysis%20-%20Sales%20Insights/TotalRevenue2017.png)
    
  2018 recorded mind blowing increase of 320.81M.

   2018
 :--------:

 ![Alt Text](https://github.com/WinnieKiarago/Data_Analytics-/blob/main/Data%20Analysis%20-%20Sales%20Insights/TotalRevenue2018.png)

 
 In 2019 the business took a downward trajectory dropping to 336.02M 
 
   2019
 :--------:
 
 ![Alt Text](https://github.com/WinnieKiarago/Data_Analytics-/blob/main/Data%20Analysis%20-%20Sales%20Insights/TotalRevenue2019.png)
 
 and dropped even further to 142.22M in 2020.

   2020
 :--------:

  ![Alt Text](https://github.com/WinnieKiarago/Data_Analytics-/blob/main/Data%20Analysis%20-%20Sales%20Insights/TotalRevenue2020.png)

### Conclusion
Overall Electrical stores has been constantly the top customer in both revenue and sales while electrical squipo has taken the bottom customer from 2018 t0 2020 by revenue.








