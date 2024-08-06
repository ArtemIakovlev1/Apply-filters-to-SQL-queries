<h1>Apply filters to SQL queries</h1>

<h2>Description</h2>

I recently discovered a potential security incident that occurred after business hours. To investigate this, I need to query the `log_in_attempts` table and review after hours login activity. I’ll use filters in SQL to create a query that identifies all failed login attempts that occurred after 18:00. (The time of the login attempt is found in the `login_time` column. The `success` column contains a value of `0` when a login attempt failed; I can use either a value of `0` or FALSE in my query to identify failed login attempts.) 
<br />

<h2>Language Used</h2>

- <b>SQL</b> 

<h2>Program walk-through</h2>

<h3>Retrieve after hours failed login attempts:</h3>

The `login_time` column in the `log_in_attempts` table contains information on when login attempts were made. Office hours end at 18:00.
The `success` column in the `log_in_attempts` table contains values of TRUE or FALSE to indicate whether the login was successful. MySQL stores Boolean values as `1` for TRUE, and `0` for FALSE. This means that TRUE is represented as `1`, and FALSE represented as `0` in the `success` column.
The `AND` operator retrieves the failed login attempts that occurred after business hours.

![Retrieve after hours failed login attempts](https://i.imgur.com/cFpW6au.png)

<h3>Retrieve login attempts on specific dates:</h3>

Our team is investigating a suspicious event that occurred on `2022-05-09`. I want to retrieve all login attempts that occurred on this day and the day before `2022-05-08`.
The `login_date` column in the `log_in_attempts` table contains information on the dates when login attempts were made.
I’ll use the `OR` operator to retrieve the failed login attempts on the specified days.

![Retrieve login attempts on specific dates](https://imgur.com/z57NNsj.png)

<h3>Retrieve login attempts outside of Mexico:</h3>

Now, my team is investigating logins that did not originate in Mexico, and I need to find this information. The country field includes entries with `MEX` and `MEXICO` so I should use the `NOT` and `LIKE` operators and the matching pattern `MEX%`.
I’ll run the following SQL query to retrieve login attempts that did not originate in Mexico.

![Retrieve login attempts outside of Mexico](https://imgur.com/dIpoLfW.png)

<h3>Retrieve employees in Marketing:</h3>

My team is updating employee machines, and I need to obtain the information about employees in the `Marketing` department who are located in all offices in the East building (such as `East-170` or `East-320`).
I’ll write a SQL query to retrieve this information from the `employees` table. I’ll select all columns and include filters on the `department` and `office` columns to return only the needed records.

![Retrieve employees in Marketing](https://imgur.com/CSeJqiH.png)

<h3>Retrieve employees in Finance or Sales:</h3>

Now, my team needs to perform a different update to the computers of all employees in the Finance or the Sales department, and I need to locate information on these employees.
I’ll write a SQL query to retrieve records for employees in the `Finance` or the `Sales` department.

![Retrieve employees in Finance or Sales](https://imgur.com/Urc0al6.png)

<h3>Retrieve all employees not in IT:</h3>

My team needs to make one more update. This update was already made to employee computers in the Information Technology department. The team needs information about employees who are not in that department. I should use the `NOT` operator to identify these employees.
I’ll write a SQL query to retrieve records for employees who are not in the `Information Technology` department.

![Retrieve all employees not in IT](https://imgur.com/DSFPzCT.png)


 <h2>Summary</h2>
 
I have practiced using SQL to
- run SQL queries to retrieve information from a database
- apply `AND`, `OR`, and `NOT` operators to filter SQL queries.
