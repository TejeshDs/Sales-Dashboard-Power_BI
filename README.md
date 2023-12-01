# Power_BI



Sales Dashboard

The objective of report is to analyze and present comprehensive insights into sales, profits, orders, profit margin and other comparision in the sales data.

its aims to provide clear understanding of key performance and trends using Power BI

SALES DASHBOARD - POWER BI

Screenshotss

TOOLS USED

Data- Sales data from Excel

data cleaning - Power query editor

data visualization - Power BI

Steps followed for Power BI Project

Gather data :

Collected the neccessary data for the project from the excel spreadsheet

Power query editor- ETL (Extract Transfer Load) :

Power query editor is powerfull tool in the power BI for cleaning data,in power query editor we can make the data to suitable for analysis that involves like removing duplicates, null values ,making proper heading for the colummn and caluculated colummns like sales,cost and profit

Create table :

created calender table by using Data Analysis Expression(DAX) functions.

Data Models :

created Data models in the power bi desktop by using manage relationship option,data models nothing but creating the relationship between the tables . the created relationship between the tables can be seen in the model view in power bi desktop.

reports :

created the visuals in the power bi desktop in the report view tab. created slicers ,charts , cards, bookmarks and many more in the report tab.

conclusion on sales

total sales is ₹ 155M, profit is ₹ 58 M, product sold is 68k

Profit margin is higher in the export channel in 2019

sales decreased is more than 5%

top 5 cities by sales are Christchurch, Hamilton, Waitakere, Manukau, Napier

Questions

sales by product comparing with last year's sales

sales by month comparing with last year's sales

profit by channel comparing with last year's profit

cities with top 5 sales

sales by customers comparing with last year's sales

show total sales, profit, profit margin, and product sold with respect to the product, channel, city and date.

create new date table

create required colummns in the date table by using DAX functions

create measures for sales,profit,cost,profit margin and any other if required.

DAX functions

used dax functions to calculate new tables,new colummns and new measures

created a new date table by using dax function:

DAX--->

    date = CALENDARAUTO()
In the date table
created new colummns :

       DAX--->
                    date full name = FORMAT('date'[Date],"dd-mmmm-yyyy")
                    date name = FORMAT('date'[Date],"dd-mmm-yyyy")
                    date_ = FORMAT('date'[Date],"dddd")
                    month = FORMAT('date'[Date],"mm")
                    month name = FORMAT('date'[Date],"mmmm")
                    monthyear = FORMAT('date'[Date],"yyyymm")
                    month with year = FORMAT('date'[Date],"mmm-yy")
                    quarter = FORMAT('date'[Date],"q")
                    short year = FORMAT('date'[Date],"yy")
                    year = FORMAT('date'[Date],"YY")
                    year name = FORMAT('date'[Date],"yyyy")
created new measures to display cards :



DAX--->
         sum of sales = SUM('Sales Orders'[sales])
         sum of profit = SUM('Sales Orders'[profit])
         sum of order = SUM('Sales Orders'[Order Quantity])
         previous year profit = CALCULATE(SUM('Sales Orders'[profit]),SAMEPERIODLASTYEAR('date'[Date]))
         previous year sales = CALCULATE(SUM('Sales Orders'[sales]),SAMEPERIODLASTYEAR('date'[Date]))
         net profit margin = DIVIDE('Sales Orders'[sum of profit],'Sales Orders'[sum of sales]).
