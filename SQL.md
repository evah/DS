#Prepare for SQL interview

###Basic
* where / group by / order by / left join / [right join](http://www.w3schools.com/sql/sql_join_right.asp) / inner join / null / not null /[insert](http://www.w3schools.com/sql/sql_insert.asp)/ [having](http://www.w3schools.com/sql/sql_having.asp) / distinct / [like](http://www.w3schools.com/sql/sql_like.asp) / [union](http://www.w3schools.com/sql/sql_union.asp) / avg / sum / min / max
* [Window functions](https://drill.apache.org/docs/sql-window-functions-introduction/)
  * Syntax
  ```
  window_function (expression) OVER (
   [ PARTITION BY expr_list ]
   [ ORDER BY order_list ][ frame_clause ] )  
  ```   
  * Value: [FIRST_VALUE()](https://docs.oracle.com/cd/B28359_01/server.111/b28286/functions059.htm)/LAG()/LAST_VALUE()/[LEAD()](https://docs.oracle.com/cd/B19306_01/server.102/b14200/functions074.htm)
  * Aggregate: AVG()/COUNT()/MAX()/MIN()/SUM()
  * Ranking: CUME_DIST()/DENSE_RANK()/[NTILE()](https://docs.oracle.com/cd/B19306_01/server.102/b14200/functions101.htm)/PERCENT_RANK()/[RANK()](https://docs.oracle.com/cd/B19306_01/server.102/b14200/functions123.htm)/ROW_NUMBER()
![rank_window](./ranking_window.png)
  * Special: unbound PROCEEDING and unbound FOLLOWING, RANGE ([details+visual](https://databricks.com/blog/2015/07/15/introducing-window-functions-in-spark-sql.html) )

>There are five types of boundaries, which are UNBOUNDED PRECEDING, UNBOUNDED FOLLOWING, CURRENT ROW, <value> PRECEDING, and <value> FOLLOWING. UNBOUNDED PRECEDING and UNBOUNDED FOLLOWING represent the first row of the partition and the last row of the partition, respectively. For the other three types of boundaries, they specify the offset from the position of the current input row and their specific meanings are defined based on the type of the frame. There are two types of frames, ROW frame and RANGE frame.



###Other
* [Spark2.0 SQL guide](https://spark.apache.org/docs/2.0.0-preview/sql-programming-guide.html)
* [window functions in Spark](https://databricks.com/blog/2015/07/15/introducing-window-functions-in-spark-sql.html)
* SQL optimization: [link1](http://www.teradata-sql.com/2012/03/sql-optimization.html), [link2](http://www.teradatahelp.com/2010/11/teradata-performance-tuning-basic-tips.html)

###Possible questions
(1)Q: what is the difference between WHERE and HAVING
* A: [HAVING is used to check conditions after the aggregation takes place.](http://stackoverflow.com/questions/287474/whats-the-difference-between-having-and-where)

(2)Q: what is the difference between GROUP BY and ORDER BY
* A: ORDER BY allows you to sort the result set according to different criteria, such as first sort by name from a-z, then sort by the price highest to lowest. GROUP BY will aggregate records by the specified columns which allows you to perform aggregation functions on non-grouped columns (such as SUM, COUNT, AVG, etc). ORDER BY can be used within the over() clause

(3)Q: how to create a view
* A: The basic CREATE VIEW syntax is as follows: CREATE VIEW view_name AS SELECT column1, column2..... FROM table_name WHERE [condition]; You can include multiple tables in your SELECT statement in very similar way as you use them in normal SQL SELECT query. In SQL, a view is a virtual table based on the result-set of an SQL statement. A view contains rows and columns, just like a real table. The fields in a view are fields from one or more real tables in the database.

(4)Q: Give an example using window functions
