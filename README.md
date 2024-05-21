# **SQL Hacker Rank Question**
![a](https://github.com/nikhildigrase17/SQL_HackerRank/assets/152486401/c84aa2f2-f935-4fbb-ad91-00d67cf14199)

## **BASIC SELECT -**

#### Q1.Query all columns (attributes) for every row in the CITY table.
The City Table is described as follows:

![aq](https://github.com/nikhildigrase17/SQL_HackerRank/assets/152486401/0bed0bb0-567e-4cef-b832-270d323fa98f)


My Solution(MySQL):
```
  SELECT *
  FROM CITY;
```
#### Q2.Query all columns for a city in CITY with the ID 1661.

My Solution(MySQL):
```
  SELECT *
  FROM CITY
  WHERE COUNTRYCODE = 'JPN';
```

#### Q3.Query all attributes of every Japanese city in the CITY table. The COUNTRYCODE for Japan is JPN.
My Solution(MySQL):
```
  SELECT *
  FROM CITY
  WHERE COUNTRYCODE = 'JPN';
```
#### Q4.Query the names of all the Japanese cities in the CITY table. The COUNTRYCODE for Japan is JPN.
My Solution(MySQL):
```
  SELECT NAME
  FROM CITY
  WHERE COUNTRYCODE = 'JPN';
```
#### Q5.Query the names of all the American cities in the CITY table. The COUNTRYCODE for America is USA.
My Solution(MySQL):
```
  SELECT NAME
  FROM CITY
  WHERE COUNTRYCODE = 'USA';
```
#### Q6.Query all columns for all American cities in the CITY table with populations larger than 100000. The CountryCode for America is USA.
My Solution(MySQL):
```
  SELECT *
  FROM CITY
  WHERE POPULATION > 100000 AND COUNTRYCODE = 'USA';
```
#### Q7.Query the NAME field for all American cities in the CITY table with populations larger than 120000. The CountryCode for America is USA.
My Solution(MySQL):
```
  SELECT NAME
  FROM CITY
  WHERE POPULATION > 120000 AND COUNTRYCODE = 'USA';
```
#### Q8.Query a list of CITY and STATE from the STATION table.
The STATION table is described as follows:

![d](https://github.com/nikhildigrase17/SQL_HackerRank/assets/152486401/31955d79-60c3-4724-a199-89f9f193657c)

My Solution(MySQL):
```
  SELECT CITY, STATE
  FROM STATION;
```
#### Q9.Query a list of CITY names from STATION for cities that have an even ID number. Print the results in any order, but exclude duplicates from the answer.
My Solution(MySQL):
```
  SELECT DISTINCT CITY
  FROM STATION
  WHERE MOD(ID, 2) = 0; 
```
#### Q10.Find the difference between the total number of CITY entries in the table and the number of distinct CITY entries in the table.
My Solution(MySQL):
```
  SELECT  COUNT(CITY) - COUNT(DISTINCT(CITY))
  FROM STATION; 
```
#### Q11.Query the two cities in STATION with the shortest and longest CITY names, as well as their respective lengths (i.e.: number of characters in the name). If there is more than one smallest or largest city, choose the one that comes first when ordered alphabetically.
My Solution(MySQL):
```
  SELECT  CITY, LENGTH(CITY)
  FROM STATION
  WHERE LENGTH(CITY) = (SELECT MIN(LENGTH(CITY)) FROM STATION) 
  OR LENGTH(CITY) = (SELECT MAX(LENGTH(CITY)) FROM STATION)
  ORDER BY LENGTH(CITY) DESC, CITY ASC LIMIT 2;
```
#### Q12.Query the list of CITY names starting with vowels (i.e., a, e, i, o, or u) from STATION. Your result cannot contain duplicates.
My Solution(MySQL):
```
  SELECT  DISTINCT CITY
  FROM STATION
  WHERE CITY REGEXP '^[A,E,I,O,U]';
```
#### Q13.Query the list of CITY names ending with vowels (a, e, i, o, u) from STATION. Your result cannot contain duplicates.
My Solution(MySQL):
```
  SELECT DISTINCT CITY
  FROM STATION
  WHERE CITY REGEXP '[A,E,I,OU,]$';
```
#### Q14.Query the list of CITY names from STATION which have vowels (i.e., a, e, i, o, and u) as both their first and last characters. Your result cannot contain duplicates.
My Solution(MySQL):
```
  SELECT DISTINCT CITY
  FROM STATION
  WHERE CITY REGEXP '^[A,E,I,O,U].*[A,E,I,O,U]$';
```
#### Q15.Query the list of CITY names from STATION that do not start with vowels. Your result cannot contain duplicates.
My Solution(MySQL):
```
  SELECT DISTINCT CITY
  FROM STATION
  WHERE CITY NOT REGEXP '^[A,E,I,O,U]';
```
#### Q16.Query the list of CITY names from STATION that do not end with vowels. Your result cannot contain duplicates.
My Solution(MySQL):
```
  SELECT DISTINCT CITY
  FROM STATION
  WHERE CITY NOT REGEXP '[A,E,I,O,U]$';
```
#### Q17.Query the list of CITY names from STATION that either do not start with vowels or do not end with vowels. Your result cannot contain duplicates.
My Solution(MySQL):
```
  SELECT DISTINCT CITY
  FROM STATION
  WHERE CITY NOT REGEXP '^[A,E,I,O,U].*[A,E,I,O,U]$';
```
#### Q18.Query the list of CITY names from STATION that either do not start with vowels and do not end with vowels. Your result cannot contain duplicates.
My Solution(MySQL):
```
  SELECT DISTINCT CITY
  FROM STATION
  WHERE CITY NOT REGEXP '^[A,E,I,O,U]'
  AND CITY NOT REGEXP '[A,E,I,O,U]$';
```

#### Q19.Query the Name of any student in STUDENTS who scored higher than Marks. Order your output by the last three characters of each name. If two or more students both have names ending in the same last three characters (i.e.: Bobby, Robby, etc.), secondary sort them by ascending ID.
The STUDENTS table is described as follows:

![V](https://github.com/nikhildigrase17/SQL_HackerRank/assets/152486401/f4c7b488-40cf-4453-89af-fcc1b943f2a6)

My Solution(MySQL):
```
  SELECT NAME
  FROM STUDENTS
  WHERE MARKS > 75
  ORDER BY RIGHT(NAME,3),ID;
```
#### Q20.Write a query that prints a list of employee names (i.e.: the name attribute) from the Employee table in alphabetical order.
The Employee table containing employee data for a company is described as follows:

![BB](https://github.com/nikhildigrase17/SQL_HackerRank/assets/152486401/73effc55-3c12-4150-9534-7c6af800f2b4)

My Solution(MySQL):
```
  SELECT NAME
  FROM EMPLOYEE
  ORDER BY NAME ASC;
```
#### Q21.Write a query that prints a list of employee names (i.e.: the name attribute) for employees in Employee having a salary greater than $2000 per month who have been employees for less than 10 months. Sort your result by ascending employee_id.
My Solution(MySQL):
```
  SELECT NAME
  FROM EMPLOYEE
  WHERE SALARY > 2000 AND MONTHS < 10
  ORDER BY EMPLOYEE_ID ASC;
```
## **AGGREGATION FUNCTION -**

#### Q22.Query a count of the number of cities in CITY having a Population larger than 1000000.
The CITY table is described as follows:

![BA](https://github.com/nikhildigrase17/SQL_HackerRank/assets/152486401/e2f5d465-e347-4731-b873-c63e6e925339)

My Solution(MySQL):
```
  SELECT COUNT(ID)
  FROM CITY
  WHERE POPULATION > 100000;
```
#### Q23.Query the total population of all cities in CITY where District is California.
My Solution(MySQL):
```
  SELECT  
  SUM(POPULATION) AS TOTAL_POPULATION
  FROM CITY
  WHERE DISTRICT = 'CALIFORNIA';
```
#### Q24. Query the average population of all cities in CITY where District is California.
My Solution(MySQL):
```
  SELECT  
  AVG(POPULATION) AS TOTAL_POPULATION
  FROM CITY
  WHERE DISTRICT = 'CALIFORNIA';
```
#### Q25. Query the average population for all cities in CITY, rounded down to the nearest integer.
My Solution(MySQL):
```
  SELECT
  ROUND(AVG(POPULATION),0) AS AVERAGE_POPULATION
  FROM CITY;
```
#### Q26. Query the sum of the populations for all Japanese cities in CITY. The COUNTRYCODE for Japan is JPN.
My Solution(MySQL):
```
  SELECT
  SUM(POPULATION) AS JAPANESE_POPULATION
  FROM CITY
  WHERE COUNTRYCODE = 'JPN';
```
#### Q27.Query the difference between the maximum and minimum populations in CITY.
My Solution(MySQL):
```
  SELECT 
  MAX(POPULATION) - MIN(POPULATION) AS DIFFRENCE
  FROM CITY;
```
#### Q28.Samantha was tasked with calculating the average monthly salaries for all employees in the EMPLOYEES table, but did not realize her keyboard's key was broken until after completing the calculation. She wants your help finding the difference between her miscalculation (using salaries with any zeros removed), and the actual average salary.
Write a query calculating the amount of error (i.e.: actual - miscalculated average monthly salaries), and round it up to the next integer.

The EMPLOYEES table is described as follows:

![M](https://github.com/nikhildigrase17/SQL_HackerRank/assets/152486401/2cb688e4-7668-4076-92b0-11e332f3ee31)

My Solution(MySQL):
```
   SELECT
   ROUND(AVG(SALARY)) - ROUND(AVG(REPLACE(SALARY, 0 , "")))
  FROM EMPLOYEES;
```
#### Q29.We define an employee's total earnings to be their monthly worked, and the maximum total earnings to be the maximum total earnings for any employee in the Employee table. Write a query to find the maximum total earnings for all employees as well as the total number of employees who have maximum total earnings. Then print these values as space-separated integers.
The Employee table containing employee data for a company is described as follows:

![S](https://github.com/nikhildigrase17/SQL_HackerRank/assets/152486401/0a631d5d-639d-4a86-a4ff-fdb32406448a)

My Solution(MySQL):
```
  SELECT 
  MAX(MONTHS * SALARY) AS EARNINGS,
  COUNT(*)
  FROM EMPLOYEE
  WHERE MONTHS * SALARY = (SELECT MAX(MONTHS * SALARY) FROM EMPLOYEE)
```
#### Q30.Query the following two values from the STATION table:
1.The sum of all values in LAT_N rounded to a scale of 2 decimal places.

2.The sum of all values in LONG_W rounded to a scale of 2 decimal places.

The STATION table is described as follows:

![J](https://github.com/nikhildigrase17/SQL_HackerRank/assets/152486401/e1d0a48f-2383-4b94-8d63-d204a9d7fff5)

My Solution(MySQL):
```
  SELECT
  ROUND(SUM(LAT_N),2) AS LAT,
  ROUND(SUM(LONG_W),2) AS LON
  FROM STATION;
```
#### Q31.Query the sum of Northern Latitudes (LAT_N) from STATION having values greater than 38.7880 and less than 137.2345. Truncate your answer to 4 decimal places.
My Solution(MySQL):
```
  SELECT
  TRUNCATE(SUM(LAT_N),4)
  FROM STATION
  WHERE LAT_N > 38.7880 AND LAT_N < 137.2345;
```
#### Q31.Query the greatest value of the Northern Latitudes (LAT_N) from STATION that is less than 137.2345. Truncate your answer to 4 decimal places.
My Solution(MySQL):
```
  SELECT
  TRUNCATE(MAX(LAT_N),4)
  FROM STATION
  WHERE LAT_N < 137.2345;
```
