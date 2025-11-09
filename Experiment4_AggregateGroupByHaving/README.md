Experiment 4: Aggregate Functions, Group By and Having Clause
NAME: NISHA J
REG NO: 212223040133
AIM
To study and implement aggregate functions, GROUP BY, and HAVING clause with suitable examples.

THEORY
Aggregate Functions
These perform calculations on a set of values and return a single value.

MIN() – Smallest value
MAX() – Largest value
COUNT() – Number of rows
SUM() – Total of values
AVG() – Average of values
Syntax:

SELECT AGG_FUNC(column_name) FROM table_name WHERE condition;
GROUP BY
Groups records with the same values in specified columns. Syntax:

SELECT column_name, AGG_FUNC(column_name)
FROM table_name
GROUP BY column_name;
HAVING
Filters the grouped records based on aggregate conditions. Syntax:

SELECT column_name, AGG_FUNC(column_name)
FROM table_name
GROUP BY column_name
HAVING condition;
Question 1 How many patients are covered by each insurance company?

Sample table:Insurance Table

name type

InsuranceID INTEGER PatientID INTEGER InsuranceCompany TEXT PolicyNumber TEXT PolicyHolder TEXT ValidityPeriod TEXT

select InsuranceCompany,count(distinct patientid) as TotalPatients from insurance group by InsuranceCompany;
Output:

image
Question 2
How many prescriptions were written for each medication?

Sample tablePrescriptions Table

For example:

Result Medication TotalPrescriptions

Ciprofloxacin 1 Doxorubicin 1 Ibuprofen 1 Levothyroxine 1 Lisinopril 1 MMR 1 Pending 1 Prenatal vita 1 Sertraline 1 Topiramate 1

select Medication,count(distinct prescriptionid) as TotalPrescriptions from Prescriptions group by medication;
Output:

image
Question 3
How many appointments are scheduled for each patient?

Sample table: Appointments Table

name type

AppointmentID INTEGER PatientID INTEGER DoctorID INTEGER AppointmentDateTime DATETIME Purpose TEXT Status TEXT For example:

Result PatientID TotalAppointments

3 3 5 2 6 1 7 1 10 3

select Patientid,count(distinct appointmentid) as TotalAppointments from Appointments group by patientid;
Output:

image
Question 4
Write a SQL query to find the Fruit with the lowest available quantity.

Note: Inventory attribute contains amount of fruits

Table: fruits

name type

id INTEGER name TEXT unit TEXT inventory INTEGER price REAL

select name as fruit_name,inventory as lowest_quantity from fruits where inventory=(select min(inventory) from fruits);
Output:

image
Question 5
Write a SQL query to find the total income of employees aged 40 or above.

Table: employee

name type

id INTEGER name TEXT age INTEGER city TEXT income INTEGER For example:

Result total_income
1800000

select sum(income) as total_income from employee where age>= 40;
Output:

image
Question 6
Write a SQL query to find the average salary of all employees?

Table: employee

name type

id INTEGER name TEXT age INTEGER city TEXT income INTEGER

select avg(income) as Average_Salary from employee;
Output:

image
Question 7
Write a SQL query to find the minimum purchase amount.

Sample table: orders

ord_no purch_amt ord_date customer_id salesman_id

70001 150.5 2012-10-05 3005 5002

70009 270.65 2012-09-10 3001 5005

70002 65.26 2012-10-05 3002 5001

select min(purch_amt) as MINIMUM from orders;
Output:

image
Question 8
Write the SQL query that accomplishes the selection of total number of products for each category from the "products" table, and includes only those products where the minimum category ID is less than 3.

Sample table: products

select category_id,count(product_name) from products where category_id<3 group by category_id ;
Output:

image
Question 9
Which cities (addresses) in the "customer1" table have an average salary lesser than Rs. 15000

Sample table: customer1

select address, AVG(salary) from customer1 group by address having avg(salary)<15000;
Output:

image
Question 10
Write the SQL query that achieves the grouping of data by age intervals using the expression (age/5)5, calculates the average age for each group, and excludes groups where the average age is not less than 24.

Sample table: customer1

select (age/5)*5 as age_group,AVG(age) from customer1 group by (age/5)*5 having avg(age)<24;
Output:

image
MODULE 3 SEB GRADE:
image
RESULT
Thus, the SQL queries to implement aggregate functions, GROUP BY, and HAVING clause have been executed successfully.
