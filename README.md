# task7_sqlite_using_python

Load SQLite database: import sqlite3 conn = sqlite3.connect("sales_data.db")  <br>
Run basic SQL: query = "SELECT Order_No, SUM(Quantity) AS total_qty, SUM(Quantity * price) AS
revenue FROM sales GROUP BY product" <br>
Load into pandas: import pandas as pd df = pd.read_sql_query(query, conn) <br>
Print results: print(df) ,br.
Plot simple bar chart: df.plot(kind='bar', x='product', y='revenue') <br>
Save chart if needed: plt.savefig("sales_chart.png")  

