SQL: Structured Query Language

SQL server names are case insensitive
### Select Statement:
Grabs whatever data you want from a database

Examples:
SELECT \* : grabs everything
SELECT \* FROM Customers; // Grabs all data from table customers
SELECT firstname, dob, email FROM customers; // Specific columns from table

### Where Clause:
Allows us to filter results by a set of criteria
SELECT * FROM Products WHERE product_type='book'; 
##### Comparison Operators:

|Operator|Description|
|---|---|
|=|Equal to|
|!=|NOT Equal to|
|<>|NOT Equal to|
|<|Less than|
|<=|Less than OR Equal to|
|>|Greater than|
|>=|Greater than OR Equal to|

SELECT * FROM Products WHERE price > 10;

##### Logical Operators
##### AND
Select * from characters where gender = "Female" and hair = "Black";
##### OR
SELECT * FROM Holidays WHERE Country='Spain' OR Country='Portugal' OR Country='Greece';
##### IN
SELECT * FROM holidays WHERE Country IN ('Spain', 'Portugal', 'Greece');
##### NOT
SELECT * FROM Holidays WHERE Country NOT IN ('North Pole', 'South Pole');

#### Like operator
(%) Wildcard operator, for pattern matching
Any string of characters can come both before and after pattern string. 

(\_) Underscore wildcard: can help us dictate how many wildcard charactes we want to search for in the string

SELECT * FROM Bands WHERE BandName like '%Blue%';  // For blue anywhere in the string
SELECT *  FROM Bands  WHERE BandName Like 'Blue%';   // Starts with Blue

To be specific with number of characters: Use _ (underscore)
For say 10 characters, 10 uderscores.
SELECT * FROM Bands  WHERE BandName Like '\__________\';_
_
### Dates
Current format: YYYY-MM-DD

SELECT firstname, dob, email FROM customers WHERE dob < '2000-01-01';

### Distinct Keyword
This means only one "distinct" data row is returned for each combination of columns in our statement.

SELECT DISTINCT Surname FROM PlayerNames;

### Sorting: Order By
Default is Ascending
SELECT FirstName, Surname FROM footballers ORDER BY Surname; 

Use DESC for descending:
SELECT FirstName, Surname FROM footballers ORDER BY Surname DESC;

### CASE statement:
The **CASE statement** in SQL allows you to create a new variable and set the values based on a series of conditions being met.

SELECT EmployeeName,  
CASE  
WHEN EmpLevel = 1 THEN 'Data Analyst'  
WHEN EmpLevel = 2 THEN 'Middle Manager'  
WHEN EmpLevel = 3 THEN 'Senior Executive'  
ELSE 'Unemployed'  
END  
  
FROM Employees;

CASE WHEN species = 'Human' THEN 'HUMAN' ELSE 'ALIEN' END

### Limit 
The LIMIT clause allows us to specify how many rows our query brings back. 

SELECT *  
FROM EnglishMonarchs  
WHERE FirstName='Elizabeth'  
ORDER BY CoronationDate  
LIMIT 1;

Doesnt work on MS SQL: but it has a statement of its own - Select Top
SELECT TOP 100 
FROM Songs 
ORDER BY RecordSales DESC;

### Count
The COUNT function allows you to count the number of rows in your table. You can use the asterisk (\*) wildcard to count everything.

SELECT COUNT(\*)
FROM WondersOfTheWorld;

