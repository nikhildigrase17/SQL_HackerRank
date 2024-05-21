# **SQL Hacker Rank Question**
![a](https://github.com/nikhildigrase17/SQL_HackerRank/assets/152486401/c84aa2f2-f935-4fbb-ad91-00d67cf14199)

## **BASIC SELECT -**

#### Q1.Query all columns (attributes) for every row in the CITY table.
The City Table is described as follows:

![aq](https://github.com/nikhildigrase17/SQL_HackerRank/assets/152486401/0bed0bb0-567e-4cef-b832-270d323fa98f)


My Solution:
```
  SELECT *
  FROM CITY;
```
#### Q2.Query all columns for a city in CITY with the ID 1661.

My Solution:
```
  SELECT *
  FROM CITY
  WHERE COUNTRYCODE = 'JPN';
```

#### Q3.Query all attributes of every Japanese city in the CITY table. The COUNTRYCODE for Japan is JPN.
My Solution:
```
  SELECT *
  FROM CITY
  WHERE COUNTRYCODE = 'JPN';
```
#### Q4.Query the names of all the Japanese cities in the CITY table. The COUNTRYCODE for Japan is JPN.
My Solution:
```
  SELECT NAME
  FROM CITY
  WHERE COUNTRYCODE = 'JPN';
```
#### Q5.Query the names of all the American cities in the CITY table. The COUNTRYCODE for America is USA.
My Solution:
```
  SELECT NAME
  FROM CITY
  WHERE COUNTRYCODE = 'USA';
```
#### Q6.Query all columns for all American cities in the CITY table with populations larger than 100000. The CountryCode for America is USA.
My Solution:
```
  SELECT *
  FROM CITY
  WHERE POPULATION > 100000 AND COUNTRYCODE = 'USA';
```
#### Q7.Query the NAME field for all American cities in the CITY table with populations larger than 120000. The CountryCode for America is USA.
My Solution:
```
  SELECT NAME
  FROM CITY
  WHERE POPULATION > 120000 AND COUNTRYCODE = 'USA';
```
#### Q8.Query a list of CITY and STATE from the STATION table.
The STATION table is described as follows:

![d](https://github.com/nikhildigrase17/SQL_HackerRank/assets/152486401/31955d79-60c3-4724-a199-89f9f193657c)

My Solution:
```
  SELECT CITY, STATE
  FROM STATION;
```
#### Q9.Query a list of CITY names from STATION for cities that have an even ID number. Print the results in any order, but exclude duplicates from the answer.
My Solution:
```
  SELECT DISTINCT CITY
  FROM STATION
  WHERE MOD(ID, 2) = 0; 
```
#### Q10.Find the difference between the total number of CITY entries in the table and the number of distinct CITY entries in the table.
My Solution:
```
  SELECT  COUNT(CITY) - COUNT(DISTINCT(CITY))
  FROM STATION; 
```
#### Q11.Query the two cities in STATION with the shortest and longest CITY names, as well as their respective lengths (i.e.: number of characters in the name). If there is more than one smallest or largest city, choose the one that comes first when ordered alphabetically.
My Solution:
```
  SELECT  CITY, LENGTH(CITY)
  FROM STATION
  WHERE LENGTH(CITY) = (SELECT MIN(LENGTH(CITY)) FROM STATION) 
  OR LENGTH(CITY) = (SELECT MIN(LENGTH(CITY)) FROM STATION)
  ORDER BY LENGTH(CITY) DESC, CITY ASC LIMIT 2; 
```
