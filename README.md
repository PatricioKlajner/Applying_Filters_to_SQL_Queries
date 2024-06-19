<h1>Applying Filters to SQL Queries</h1>

<h2>Description</h2>
My organization is working to make their system more secure. It is my job to ensure the system is safe, investigate all potential security issues, and update employee computers as needed. The following steps provide examples of how I used SQL with filters to perform security-related tasks.

<h2>Project Walkthrough</h2>

<h3>Retrieve after hours failed login attempts</h3>
There was a potential security incident that occurred after business hours (after 18:00). All after hours login attempts that failed need to be investigated.
<br />
<br />
The following code demonstrates how I created a SQL query to filter for failed login attempts that occurred after business hours.
<br />
<br />

<p align="center">
<img src="https://i.imgur.com/0eSDaYe.png" height="70%" width="70%" alt="SQL 1"/> </p>

The first part of the screenshot is my query, and the second part is the output. This query filters for failed login attempts that occurred after 18:00. First, I started by selecting all data from the log_in_attempts table. Then, I used a WHERE clause with an AND operator to filter my results to output only login attempts that occurred after 18:00 and were unsuccessful. The first condition is login_time > '18:00', which filters for the login attempts that occurred after 18:00. The second condition is success = FALSE, which filters for the failed login attempts.

<h3>Retrieve login attempts on specific dates</h3>
A suspicious event occurred on 2022-05-09. Any login activity that happened on 2022-05-09 or on the day before needs to be investigated.
<br />
<br />
The following code demonstrates how I created an SQL query to filter for login attempts that occurred on specific dates.
<br />
<br />

<p align="center">
<img src="https://i.imgur.com/KKGiiZF.png" height="70%" width="70%" alt="SQL 2"/> </p>

The first part of the screenshot is my query, and the second part is a portion of the output. This query returns all login attempts that occurred on 2022-05-09 or 2022-05-08. First, I started by selecting all data from the log_in_attempts table. Then, I used a WHERE clause with an OR operator to filter my results to output only login attempts that occurred on either 2022-05-09 or 2022-05-08. The first condition is login_date = '2022-05-09', which filters for logins on 2022-05-09. The second condition is login_date = '2022-05-08', which filters for logins on 2022-05-08.

<h3>Retrieving login attempts outside of Mexico</h3>
After investigating the organization’s data on login attempts, I believe there is an issue with the login attempts that occurred outside of Mexico. These login attempts should be investigated.
<br />
<br />
The following code demonstrates how I created a SQL query to filter for login attempts that occurred outside of Mexico.
<br />
<br />

<p align="center">
<img src="https://i.imgur.com/uvlohA7.png" height="70%" width="70%" alt="SQL 3"/> </p>

The first part of the screenshot is my query, and the second part is a portion of the output. This query returns all login attempts that occurred in countries other than Mexico. First, I started by selecting all data from the log_in_attempts table. Then, I used a WHERE clause with NOT to filter for countries other than Mexico. I used LIKE with MEX% as the pattern to match because the dataset represents Mexico as MEX and MEXICO. The percentage sign (%) represents any number of unspecified characters when used with LIKE.

<h3>Retrieving employees in Marketing</h3>
My team wants to update the computers for certain employees in the Marketing department. To do this, I have to get information on which employee machines to update.
<br />
<br />
The following code demonstrates how I created a SQL query to filter for employee machines from employees in the Marketing department in the East building.
<br />
<br />

<p align="center">
<img src="https://i.imgur.com/nRWBcx8.png" height="70%" width="70%" alt="SQL 4"/> </p>

The first part of the screenshot is my query, and the second part is the output. This query returns all employees in the Marketing department in the East building. First, I started by selecting all data from the employees table. Then, I used a WHERE clause with AND to filter for employees who work in the Marketing department and in the East building. I used LIKE with East% as the pattern to match because the data in the office column represents the East building with the specific office number. The first condition is the department = 'Marketing' portion, which filters for employees in the Marketing department. The second condition is the office LIKE 'East%' portion, which filters for employees in the East building.

<h3>Retrieving employees in Finance or Sales</h3>
The machines for employees in the Finance and Sales departments also need to be updated. Since a different security update is needed, I have to get information on employees only from these two departments.
<br />
<br />
The following code demonstrates how I created a SQL query to filter for employee machines from employees in the Finance or Sales departments.
<br />
<br />

<p align="center">
<img src="https://i.imgur.com/6D2644Y.png" height="70%" width="70%" alt="SQL 5"/> </p>

The first part of the screenshot is my query, and the second part is a portion of the output. This query returns all employees in the Finance and Sales departments. First, I started by selecting all data from the employees table. Then, I used a WHERE clause with OR to filter for employees who are in the Finance and Sales departments. I used the OR operator instead of AND because I want all employees who are in either department. The first condition is department = 'Finance', which filters for employees from the Finance department. The second condition is department = 'Sales', which filters for employees from the Sales department.

<h3>Retrieving al employees not in IT</h3>
My team needs to make one more security update on employees who are not in the Information Technology department. To make the update, I first have to get information on these employees.
<br />
<br />
The following demonstrates how I created a SQL query to filter for employee machines from employees not in the Information Technology department.
<br />
<br />

<p align="center">
<img src="https://i.imgur.com/gTqO9SY.png" height="70%" width="70%" alt="SQL 6"/> </p>

The first part of the screenshot is my query, and the second part is a portion of the output. The query returns all employees not in the Information Technology department. First, I started by selecting all data from the employees table. Then, I used a WHERE clause with NOT to filter for employees not in this department.

<h2>Summary</h2>
I applied filters to SQL queries to get specific information on login attempts and employee machines. I used two different tables, log_in_attempts and employees. I used the AND, OR, and NOT operators to filter for the specific information needed for each task. I also used LIKE and the percentage sign (%) wildcard to filter for patterns.
