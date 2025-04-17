# task7_sqlite_using_python

https://github.com/surendra-92/task7_sqlite_using_python/blob/main/task7.ipynb
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



 
 
