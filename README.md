<h1>Apply-SQL-Filters-Queries</h1>

<h2>Description</h2>
Conducted a comprehensive analysis of employee and login attempt data to investigate potential security issues within the organization. This project focused on identifying patterns and anomalies in login activities and employee machine usage through SQL queries. The investigation included filtering and retrieving specific records using conditions on date ranges, event IDs, department locations, and login success status.
<br />


<h2>Languages Used</h2>

- <b>SQL</b> 
  



<h2>Program walk-through:</h2>

<b> 1-Retrieve after hours failed login attempts </b>: 


You recently discovered a potential security incident that occurred after business hours. To investigate this, you need to query the log_in_attempts table and review after hours login activity. Use filters in SQL to create a query that identifies all failed login attempts that occurred after 18:00. (The time of the login attempt is found in the login_time column. The success column contains a value of 0 when a login attempt failed; you can use either a value of 0 or FALSE in your query to identify failed login attempts.)

Describe your query and how it works in the Retrieve after hours failed login attempts section of the Apply filters to SQL queries template. 

<b><u> *SOLUTION: </u></b>

There was a potential security incident that occurred after business hours (after 18:00). All after hours login attempts that failed need to be investigated.

The following code demonstrates how I created a SQL query to filter for failed login attempts that occurred after business hours.

<br/>
<img src="https://github.com/user-attachments/assets/39ab453f-d304-48c6-9064-bcd7d83a876d" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />

This query filters for failed login attempts that occurred after 18:00. First, I started by selecting all data from the log_in_attempts table. Then, I used a WHERE clause with an AND operator to filter my results to output only login attempts that occurred after 18:00 and were unsuccessful. The first condition is login_time > '18:00', which filters for the login attempts that occurred after 18:00. The second condition is success = FALSE, which filters for the failed login attempts. 

<b> 2-Retrieve login attempts on specific dates </b>: 

A suspicious event occurred on 2022-05-09. To investigate this event, you want to review all login attempts which occurred on this day and the day before. Use filters in SQL to create a query that identifies all login attempts that occurred on 2022-05-09 or 2022-05-08.

Describe your query and how it works in the Retrieve login attempts on specific dates section of the Apply filters to SQL queries template. 

<b><u> *SOLUTION: </u></b>

A suspicious event occurred on 2022-05-09. Any login activity that happened on 2022-05-09 or on the day before needs to be investigated.

The following code demonstrates how I created a SQL query to filter for login attempts that occurred on specific dates.

<br/>
<img src="https://github.com/user-attachments/assets/336d2fd6-228f-41f4-b582-6ff468970f82" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />

This query returns all login attempts that occurred on 2022-05-09 or 2022-05-08. First, I started by selecting all data from the log_in_attempts table. Then, I used a WHERE clause with an OR operator to filter my results to output only login attempts that occurred on either 2022-05-09 or 2022-05-08. The first condition is login_date = '2022-05-09', which filters for logins on 2022-05-09. The second condition is login_date = '2022-05-08', which filters for logins on 2022-05-08.


<b> 3-Retrieve login attempts outside of Mexico</b>: 

There’s been suspicious activity with login attempts, but the team has determined that this activity didn't originate in Mexico. Now, you need to investigate login attempts that occurred outside of Mexico. Use filters in SQL to create a query that identifies all login attempts that occurred outside of Mexico.

Describe your query and how it works in the Retrieve login attempts on specific dates section of the Apply filters to SQL queries template. 

<b><u> *SOLUTION: </u></b>

After investigating the organization’s data on login attempts, I believe there is an issue with the login attempts that occurred outside of Mexico. These login attempts should be investigated.

The following code demonstrates how I created a SQL query to filter for login attempts that occurred outside of Mexico. 


<br/>
<img src="https://github.com/user-attachments/assets/eb0132c6-8d02-4dfd-ae95-1e5285a8a8fd" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />

This query returns all login attempts that occurred in countries other than Mexico. First, I started by selecting all data from the log_in_attempts table. Then, I used a WHERE clause with NOT to filter for countries other than Mexico. I used LIKE with MEX% as the pattern to match because the dataset represents Mexico as MEX and MEXICO. The percentage sign (%) represents any number of unspecified characters when used with LIKE. 


<b> 4-Retrieve employees in Marketing</b>: 

Your team wants to perform security updates on specific employee machines in the Marketing department. You’re responsible for getting information on these employee machines and will need to query the employees table. Use filters in SQL to create a query that identifies all employees in the Marketing department for all offices in the East building.

The department of the employee is found in the department column, which contains values that include Marketing. The office is found in the office column. Some examples of values in this column are East-170, East-320, and North-434.

<b><u> *SOLUTION: </u></b>

My team wants to update the computers for certain employees in the Marketing department. To do this, I have to get information on which employee machines to update.

The following code demonstrates how I created a SQL query to filter for employee machines from employees in the Marketing department in the East building.


<br/>
<img src="https://github.com/user-attachments/assets/07a29e61-4e93-401f-afbc-76a2aec8e920"/>
<br />

This query returns all employees in the Marketing department in the East building. First, I started by selecting all data from the employees table. Then, I used a WHERE clause with AND to filter for employees who work in the Marketing department and in the East building. I used LIKE with East% as the pattern to match because the data in the office column represents the East building with the specific office number. The first condition is the department = 'Marketing' portion, which filters for employees in the Marketing department. The second condition is the office LIKE 'East%' portion, which filters for employees in the East building.


<b> 5-Retrieve employees in Finance or Sales</b>: 

Your team now needs to perform a different security update on machines for employees in the Sales and Finance departments. Use filters in SQL to create a query that identifies all employees in the Sales or Finance departments. 

<b><u> *SOLUTION: </u></b>

The machines for employees in the Finance and Sales departments also need to be updated. Since a different security update is needed, I have to get information on employees only from these two departments.

The following code demonstrates how I created a SQL query to filter for employee machines from employees in the Finance or Sales departments.

<br/>
<img src="https://github.com/user-attachments/assets/c34efff0-c4c8-451f-9438-f9e5de7b6342"/>
<br />

This query returns all employees in the Finance and Sales departments. First, I started by selecting all data from the employees table. Then, I used a WHERE clause with OR to filter for employees who are in the Finance and Sales departments. I used the OR operator instead of AND because I want all employees who are in either department. The first condition is department = 'Finance', which filters for employees from the Finance department. The second condition is department = 'Sales', which filters for employees from the Sales department.


<b> 6-Retrieve all employees not in IT </b>: 

Your team needs to make one more update to employee machines. The employees who are in the Information Technology department already had this update, but employees in all other departments need it. Use filters in SQL to create a query which identifies all employees not in the IT department.

Describe your query and how it works in the Retrieve all employees not in IT section of the Apply filters to SQL queries template. 

<b><u> *SOLUTION: </u></b>

My team needs to make one more security update on employees who are not in the Information Technology department. To make the update, I first have to get information on these employees.

The following demonstrates how I created a SQL query to filter for employee machines from employees not in the  Information Technology department.

<br/>
<img src="https://github.com/user-attachments/assets/520ca178-19fe-4b61-9df2-b93b5a4845cf"/>
<br />

The query returns all employees not in the Information Technology department. First, I started by selecting all data from the employees table. Then, I used a WHERE clause with NOT to filter for employees not in this department.

<h2>Summary</h2>

I applied filters to SQL queries to get specific information on login attempts and employee machines. I used two different tables, log_in_attempts and employees. I used the AND, OR, and NOT operators to filter for the specific information needed for each task. I also used LIKE and the percentage sign (%) wildcard to filter for patterns.

