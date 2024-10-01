I had the privilege of working with Super Store Analysis which presented a wide range of tables. 

# Super Store Analytic Dashboard

### Dashboard Link : https://app.powerbi.com/groups/me/reports/1f921a4e-a5d2-4d58-ad9d-9678d7c607ff/e6843778faafe4a928bc?experience=power-bi

In this challenge, we have given access to a rich data set that covers a variety of variables related to Super Stores. Our task is to identify the Metrics of Sales, Profit, % of Returned Orders, To Show % Change vs Previous Year. Compare Sales Performance versus previous Year over time. To Determine the most profitable product and the most loss making product. To Find out the place where most of the profit is happening and Sales by Segment.

📌 TOOLS USED
1. Power BI
2. Excel
3. SQL

📌 THE REPORT
The resulting dashboard encompasses vital key performance indicators (KPIs) including Timeline Sales on the basis of Yearly vs Previous Years. Profits according to states as well as aesthetically captivating visual representations and profound analytical interpretations.

📌DATA PREPARATION
To ensure the quality of the data, an essential step involved meticulous data cleaning procedures performed within Power BI's Power Query Editor. Corrections were made to erroneous data types, while the creation of calculated columns and measures facilitated the derivation of pertinent KPIs required for the analysis.

 Following Measures was written to find % Returned Order
 
         % Returned Orders = VAR Percentage = 
    DIVIDE(
        DISTINCTCOUNT(Returns[Order ID]),
        DISTINCTCOUNT(Orders[Order ID])
    ) RETURN 
    FORMAT(Percentage, "Percent")

    
Following Measures was written to find Profit


      Profit = SUM( Orders[Profit] )

Following Measures was written to find Sales
   
      Sales = SUM( Orders[Sales] )

Following Measures was written to find % Returned Orders PY
  
    % returned orders PY = CALCULATE(
    [% returned orders],
    SAMEPERIODLASTYEAR( 'Date Table'[Date] ))

Following Measures was written to find Profit PY

    Profit PY = CALCULATE(
    [Profit],
    SAMEPERIODLASTYEAR( 'Date Table'[Date] ))

Following Measures was written to find Sales PY

    Sales PY = CALCULATE(
    [Sales],
    SAMEPERIODLASTYEAR( 'Date Table'[Date] ))

Following Measures was written to find vs PY - % returned orders

    vs PY - % returned orders = [% Returned Orders] - [% returned orders PY]

Following Measures was written to find vs PY - Profit

    vs PY - Profit = DIVIDE(
    [Profit] - [Profit PY],
    [Profit PY])

Following Measures was written to find vs PY - Sales

    vs PY - Sales = DIVIDE(
    [Sales] - [Sales PY],
    [Sales PY])

# Snapshot of Dashboard (Power BI Service)

![Dashboard_Snap]![Super Store img2](https://github.com/user-attachments/assets/109b0ebe-3d8d-4a2e-8427-1a39aea5ce52)



