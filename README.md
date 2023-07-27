<h1>Applying Filters To SQL Queries</h1>

<h2>Languages and Utilities Used</h2>

- <b>SQL</b> 
- <b>Table Formats Document</b>

<h2>Description</h2>

My (fictitious) organization is working to make their system more secure. It is my job to ensure the system is safe, investigate all potential security issues, and update employee computers as needed. The following steps provide examples of how I used SQL with filters to perform security-related tasks.
<br />

<h2>Retrieving After Hours Failed Login Attempts</h2>
After business hours (after 18:00), a potential security incident occurred, warranting investigation into all failed login attempts during that time.

Below is the SQL query I developed to filter and analyze the failed login attempts that occurred after business hours:
<p align="center">
<img src="https://imgur.com/8gbcSf8.png" height="80%" width="80%" alt="Failed Login Attempts After Business Hours"/> </p>

In the screenshot, the query's purpose is to filter for failed login attempts that occurred after 18:00. The process started by selecting all data from the log_in_attempts table. Then, a WHERE clause with an AND operator was used to narrow down the results to show only login attempts that occurred after 18:00 and were unsuccessful. The first condition, login_time > '18:00', focuses on login attempts that happened after 18:00, while the second condition, success = FALSE, filters for the failed login attempts.


<h2>Retrieving Login Attempts On Specific Dates</h2>

On May 9, 2022, a concerning event took place, prompting the need for investigation into any login activity that occurred on that date or the day before.

To facilitate the investigation, I have crafted an SQL query that effectively filters and identifies login attempts that occurred on the specified dates. The code below demonstrates the query:
<p align="center">
<img src="https://imgur.com/OPtvtNe.png" height="80%" width="80%" alt="Login Attempts On Specific Dates"/> </p>

In this query, I retrieved login attempts data from the log_in_attempts table for two specific dates, 2022-05-09 and 2022-05-08. To accomplish this, I used a WHERE clause with the OR operator to filter the results. The first condition, login_date = '2022-05-09', isolates login attempts that occurred on May 9th, 2022. The second condition, login_date = '2022-05-08', narrows down login attempts on May 8th, 2022. By combining these conditions with the OR operator, the query provides a comprehensive output of all login attempts from both dates.


<h2>Retrieving Login Attempts Outside Of Mexico</h2>

Upon thorough examination of the organization's login attempt data, it has come to my attention that there may be a concern with the login attempts originating outside of Mexico. It is essential to conduct a detailed investigation into these particular login activities.

To address this issue, I have formulated an SQL query that filters and isolates login attempts originating from locations outside of Mexico. The code below showcases the implementation of this SQL query:
<p align="center">
<img src="https://imgur.com/gDgj0KY.png" height="80%" width="80%" alt="Login Attempts Outside Of Mexico"/> </p>

In the screenshot, you can see my query and a portion of the output. The query is designed to retrieve all login attempts from the log_in_attempts table that occurred in countries other than Mexico.

To achieve this, I began by selecting all data from the log_in_attempts table. Next, I utilized a WHERE clause with NOT to exclude records with Mexico as the country. To account for variations in how Mexico is represented in the dataset (i.e., MEX and MEXICO), I used the LIKE operator with the pattern "MEX%". The percentage sign (%) acts as a wildcard, matching any number of unspecified characters when used with LIKE. This ensures that any country starting with "MEX" is excluded from the results, effectively leaving us with login attempts from countries other than Mexico.

<h2>Retrieving Employees In Marketing</h2>

As a part of my team's efforts to upgrade the computers for specific employees in the Marketing department, I needed to gather information about which employee machines needed updates.

To achieve this, I developed a SQL query to filter and identify employee machines belonging to the Marketing department within the East building. The following code snippet showcases how I implemented this query:
<p align="center">
<img src="https://imgur.com/6GhNHNb.png" height="80%" width="80%" alt="Retrieving Employees In Marketing"/> </p>

In the screenshot provided, the query and output showcase the retrieval of employees working in the Marketing department within the East building. Initially, I selected all data from the employees table. Next, I utilized a WHERE clause with an AND operator to filter for employees belonging to the Marketing department and working in the East building. To achieve this, I employed the LIKE operator with the pattern 'East%' to match the data in the office column representing the East building along with the specific office number. The first condition, department = 'Marketing', narrows down the search to employees in the Marketing department, while the second condition, office LIKE 'East%', filters for those in the East building.

<h2>Retrieving Employees In Finance Or Sales</h2>

In addition to the general system updates, it is necessary to update the machines used by employees in the Finance and Sales departments. As these departments require a specific security update, I focused on gathering information solely from employees within these two departments.

To achieve this, I have developed a SQL query that effectively filters and selects employee machines associated with the Finance and Sales departments. The following code exemplifies how this query was created to ensure the targeted updates are applied accordingly.
<p align="center">
<img src="https://imgur.com/6q16Rj7.png" height="80%" width="80%" alt="Retrieving Employees In Finance Or Sales"/> </p>

In the screenshot, the query I executed focuses on retrieving specific data from the employees table. The output displays employees who belong to either the Finance or Sales departments.

To achieve this, I began by selecting all records from the employees table. Next, I applied a WHERE clause with the OR operator, as I wanted to include employees from either the Finance or Sales department. The first condition used was department = 'Finance', which filters for employees in the Finance department. The second condition, department = 'Sales', filters for employees in the Sales department. By using the OR operator, I ensure that the query returns all employees who are in either department, meeting the criteria specified.

<h2>Retrieving All Employees Not In IT</h2>

To implement an additional security update for employees outside the Information Technology department, my team requires specific information about these employees. To achieve this, I crafted an SQL query to filter for employee machines that do not belong to the Information Technology department. This query allows us to gather the necessary data and proceed with the security update effectively.
<p align="center">
<img src="https://imgur.com/l3j8WoD.png" height="80%" width="80%" alt="Retrieving All Employees Not In IT"/> </p>

In the screenshot, you can see my query and a section of the output. The purpose of the query is to retrieve all employees who are not part of the Information Technology department. To achieve this, I began by selecting all data from the employees table. Subsequently, I utilized a WHERE clause with NOT to filter and exclude employees belonging to the Information Technology department.

<h2>Summary</h2>

To extract specific information on login attempts and employee machines, I implemented filters on SQL queries. Utilizing two distinct tables, namely log_in_attempts and employees, I employed the AND, OR, and NOT operators to target the exact details required for each task. Additionally, I leveraged the LIKE operator and the percentage sign (%) wildcard to filter for specific patterns in the data.
