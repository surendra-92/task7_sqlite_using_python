# task7_sqlite_using_python

https://github.com/surendra-92/task7_sqlite_using_python/blob/main/task7.ipynb  <br>
 Top 10 order with total Revenue  
 Order_No <br> 
 Total_revenue  <br>
 Total_Quantity <br> 

 # Steps We Followed: <br>
Loaded CSV Data using pandas <br>
→ pd.read_csv() with proper encoding (latin1) <br>

Created SQLite Database in Memory  <br>
→ Using sqlite3.connect(':memory:')  <br>

Saved the DataFrame as SQL Table  <br>
→ df.to_sql('sales', conn, index=False)  <br>

Wrote SQL Query  <br>
→ Summarized:  <br>

SUM(QUANTITYORDERED) → Total Quantity  <br>

SUM(QUANTITYORDERED * PRICEEACH) → Total Revenue <br>
→ Grouped by PRODUCTCODE  <br>
→ Ordered by total_revenue DESC  <br>
→ Limited to top 10 products <br>

Executed the SQL Query in Python  <br>
→ pd.read_sql_query(query, conn)   <br>

Plotted Bar Chart Using Matplotlib   <br>
→ X-axis: PRODUCTCODE   <br>
→ Y-axis: Total Revenue    <br>
→ Customized size, colors, and labels   <br>

Saved the Plot as an Image   <br>
→ Used plt.savefig('filename.png')  <br>
→ Called before plt.show() to avoid blank images   <br>   


1.How did you connect Python to a database? <br>
 A. import sqlite3 
    conn = sqlite3.connect('sales_data') 
    df.to_sql('sales_data', conn, index=False, if_exists='replace') <br>
2.What SQL query did you run? <br>
A.SELECT <br>
            Order_No,  <br>
            SUM(Quantity) as Total_Quantity,  <br>
            SUM(Quantity * Price) as Total_Revenue   <br>
     FROM sales_data   <br>
     GROUP BY Order_No  <br>
     ORDER BY Total_Revenue DESC  <br>
     LIMIT 10;  <br>
          
3. What does GROUP BY do?  <br>
GROUP BY groups rows that have the same values in specified columns. <br>
In our case, it grouped all sales by PRODUCTCODE, so we could sum the quantity and revenue per product. <br>

💰 4. How did you calculate revenue?  <br>
We calculated revenue inside the SQL query using: <br>

 
SUM(QUANTITYORDERED * PRICEEACH) AS total_revenue  <br>
That multiplies the quantity of each item sold by its price, and then adds it up for each product.  <br>

📊 5. How did you visualize the result? <br>
We used matplotlib in Python: <br>

 
plt.bar(summary_df['PRODUCTCODE'], summary_df['total_revenue'])  <br>
This created a bar chart showing total revenue for each top-selling product. We also saved it as an image using:  <br>
 
plt.savefig('top_10_products_revenue.png')  <br>
🐼 6. What does pandas do in your code?   <br>
Loads CSV data into a DataFrame: pd.read_csv()  <br>

Executes SQL queries with the connection: pd.read_sql_query()  <br>

Handles tabular data (like Excel for Python)  <br>

Allows filtering, grouping, and analyzing data easily  <br>

🧠 7. What’s the benefit of using SQL inside Python?  <br>
✅ Combines SQL’s power to query large datasets with Python’s ability to:  <br>

Automate workflows  <br>

Create visualizations <br>

Do further analysis with libraries (pandas, numpy, matplotlib) <br>

Build dashboards or apps later  <br>

It’s the best of both worlds: data wrangling + analysis + automation.  <br>
 
🧪 8. Could you run the same SQL query directly in DB Browser for SQLite?  <br>
Yes, absolutely!
If you save the sales table into a real .db file, you can:  <br>

Open the .db file in DB Browser for SQLite   <br>

Go to the Execute SQL tab    <br>

Paste and run the same SQL query    <br>

You'll get the same result — just without the Python chart.    <br>


 
 
