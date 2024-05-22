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
#### Q32.Query the greatest value of the Northern Latitudes (LAT_N) from STATION that is less than 137.2345. Truncate your answer to 4 decimal places.
My Solution(MySQL):
```
  SELECT
  TRUNCATE(MAX(LAT_N),4)
  FROM STATION
  WHERE LAT_N < 137.2345;
```
#### Q33.Query the Western Longitude (LONG_W) for the largest Northern Latitude (LAT_N) in STATION that is less than 137.2345. Round your answer to 4 decimal places.
My Solution(MySQL):
```
  SELECT
  ROUND(LONG_W,4)
  FROM STATION
  WHERE LAT_N = (SELECT MAX(LAT_N) FROM STATION WHERE LAT_N < 137.2345);
```
#### Q34.Query the smallest Northern Latitude (LAT_N) from STATION that is greater than 38.7780. Round your answer to 4 decimal places.
My Solution(MySQL):
```
  SELECT 
  ROUND(MIN(LAT_N),4)
  FROM STATION
  WHERE LAT_N > 38.7780;
```
#### Q35.Query the Western Longitude (LONG_W)where the smallest Northern Latitude (LAT_N) in STATION is greater than 38.7780. Round your answer to 4 decimal places.
My Solution(MySQL):
```
  SELECT
  ROUND(LONG_W,4)
  FROM STATION
  WHERE LAT_N = (SELECT MIN(LAT_N) FROM STATION WHERE LAT_N > 38.7780);
```
#### Q36.Consider P1(a,b) and P2(c,d) to be two points on a 2D plane.
a happens to equal the minimum value in Northern Latitude (LAT_N in STATION).

b happens to equal the minimum value in Western Longitude (LONG_W in STATION).

c happens to equal the maximum value in Northern Latitude (LAT_N in STATION).

d happens to equal the maximum value in Western Longitude (LONG_W in STATION). Query the Manhattan Distance between points P1 and P2 and round it to a scale of 4 decimal places.
My Solution(MySQL):
```
  SELECT 
  ROUND((MAX(LAT_N)-MIN(LAT_N)) + (MAX(LONG_W)-MIN(LONG_W)),4) AS Distance 
  FROM STATION;
```
#### Q37.Consider P1(a,c) and P2(b,d) to be two points on a 2D plane where (a,b) are the respective minimum and maximum values of Northern Latitude (LAT_N) and (c,d) are the respective minimum and maximum values of Western Longitude (LONG_W) in STATION.
Query the Euclidean Distance between points P1 and P2 and format your answer to display 4 decimal digits.
My Solution(MySQL):
```
  SELECT
  ROUND(SQRT(POWER(MAX(LAT_N)-MIN(LAT_N),2) + POWER(MAX(LONG_W)-MIN(LONG_W),2)),4)
  FROM STATION;
```
#### Q38.A median is defined as a number separating the higher half of a data set from the lower half. Query the median of the Northern Latitudes (LAT_N) from STATION and round your answer to 4 decimal places.
My Solution(MySQL):
```
  SELECT CAST(ROUND(AVG(LAT_N),4) AS DECIMAL(10,4))
  FROM (SELECT LAT_N, ROW_NUMBER() OVER(ORDER BY LAT_N) AS RowNumber, 
  COUNT(*) OVER() AS TotalRows FROM STATION) AS temp 
  WHERE RowNumber IN ((TotalRows + 1) / 2, (TotalRows + 2) / 2);
```
## **Basic Join -**

#### Q39.Given the CITY and COUNTRY tables, query the sum of the populations of all cities where the CONTINENT is 'Asia'.
Note: CITY.CountryCode and COUNTRY.Code are matching key columns.

The CITY and COUNTRY tables are described as follows:

![C](https://github.com/nikhildigrase17/SQL_HackerRank/assets/152486401/5ab008f0-4658-4503-bbd2-556b198a4132)

![B](https://github.com/nikhildigrase17/SQL_HackerRank/assets/152486401/facb983b-7242-4151-9aef-ea40574ab930)

My Solution(MySQL):
```
  SELECT
  SUM(C.POPULATION)
  FROM CITY AS C
  INNER JOIN COUNTRY AS CT
  ON C.COUNTRYCODE = CT.CODE
  WHERE CONTINENT = 'ASIA';
```
#### Q40.Given the CITY and COUNTRY tables, query the names of all cities where the CONTINENT is 'Africa'.
Note: CITY.CountryCode and COUNTRY.Code are matching key columns.
My Solution(MySQL):
```
  SELECT
  C.NAME
  FROM CITY AS C
  INNER JOIN COUNTRY AS CT
  ON C.COUNTRYCODE = CT.CODE
  WHERE CONTINENT  = 'AFRICA';
```
#### Q41.Given the CITY and COUNTRY tables, query the names of all the continents (COUNTRY.Continent) and their respective average city populations (CITY.Population) rounded down to the nearest integer.
Note: CITY.CountryCode and COUNTRY.Code are matching key columns.
My Solution(MySQL):
```
  SELECT
  CT.CONTINENT,
  FLOOR(AVG(C.POPULATION))
  FROM COUNTRY AS CT
  INNER JOIN CITY AS C
  ON C.COUNTRYCODE = CT.CODE
  GROUP BY CT.CONTINENT;
```
#### Q41.Query a count of the number of cities in CITY having a Population larger than 100000.
My Solution(MySQL):
```
  SELECT
  CT.CONTINENT,
  FLOOR(AVG(C.POPULATION))
  FROM COUNTRY AS CT
  INNER JOIN CITY AS C
  ON C.COUNTRYCODE = CT.CODE
  GROUP BY CT.CONTINENT;
```
#### Q42.Write a query identifying the type of each record in the TRIANGLES table using its three side lengths. Output one of the following statements for each record in the table:

Equilateral: It's a triangle with  sides of equal length.
Isosceles: It's a triangle with  sides of equal length.
Scalene: It's a triangle with  sides of differing lengths.
Not A Triangle: The given values of A, B, and C don't form a triangle.

My Solution(MySQL):
```
  SELECT CASE
  WHEN A + B <= C OR A + C <= B OR B + C <= A THEN 'Not A Triangle'
  WHEN A = B AND B = C THEN 'Equilateral'
  WHEN A = B OR B = C OR A = C THEN 'Isosceles'
  ELSE 'Scalene'
  END
  FROM TRIANGLES;
```
#### Q43.Samantha interviews many candidates from different colleges using coding challenges and contests. Write a query to print the contest_id, hacker_id, name, and the sums of total_submissions, total_accepted_submissions, total_views, and total_unique_views for each contest sorted by contest_id. Exclude the contest from the result if all four sums are .
My Solution(MySQL):
```
  SELECT A.CONTEST_ID, A.HACKER_ID, A.NAME, 
        SUM(TOTAL_SUBMISSIONS) AS TOTAL_SUBMISSIONS, 
        SUM(TOTAL_ACCEPTED_SUBMISSIONS) AS TOTAL_ACCEPTED_SUBMISSIONS,
        SUM(TOTAL_VIEWS) AS TOTAL_VIEWS,
        SUM(TOTAL_UNIQUE_VIEWS) AS TOTAL_UNIQUE_VIEWS
FROM CONTESTS AS A
LEFT JOIN COLLEGES AS B
    ON A.CONTEST_ID = B.CONTEST_ID
LEFT JOIN CHALLENGES AS C
    ON B.COLLEGE_ID = C.COLLEGE_ID 
LEFT JOIN (SELECT CHALLENGE_ID, SUM(TOTAL_VIEWS) AS TOTAL_VIEWS, 
                  SUM(TOTAL_UNIQUE_VIEWS) AS TOTAL_UNIQUE_VIEWS
           FROM VIEW_STATS
           GROUP BY CHALLENGE_ID) AS D 
    ON C.CHALLENGE_ID = D.CHALLENGE_ID 
LEFT JOIN (SELECT CHALLENGE_ID, SUM(TOTAL_SUBMISSIONS) AS TOTAL_SUBMISSIONS, 
                  SUM(TOTAL_ACCEPTED_SUBMISSIONS) AS TOTAL_ACCEPTED_SUBMISSIONS
           FROM SUBMISSION_STATS
           GROUP BY CHALLENGE_ID) AS E
    ON C.CHALLENGE_ID = E.CHALLENGE_ID
GROUP BY A.CONTEST_ID, A.HACKER_ID, A.NAME
HAVING (TOTAL_SUBMISSIONS + TOTAL_ACCEPTED_SUBMISSIONS + TOTAL_VIEWS + TOTAL_UNIQUE_VIEWS) > 0 
ORDER BY A.CONTEST_ID;
```
