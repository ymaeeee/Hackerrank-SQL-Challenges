<h1> Hackerrank's SQL Basic Challenges </h1>

## File Description
<p> This markdown file contains the basic SQL challenges from Hackerrank that I have solved. Feel free to check my solutions for each problems.</p>

### SQL Challenges/Problems

**Topic:** Revising the Select Query I<br>
**Problem:** Query all columns for all American cities in the CITY table with populations larger than 100000. The CountryCode for America is USA.

**CITY**
| Field       | Type         |
|-------------|--------------|
| ID          | NUMBER       |
| NAME        | VARCHAR2(17) |
| COUNTRYCODE | VARCHAR2(3)  |
| DISTRICT    | VARCHAR2(20) |
| POPULATION  | NUMBER       |

**Solution:**
``` sql
SELECT * FROM city
WHERE countrycode = 'USA' AND population >= 100000;
```
<br>

**Topic:** Revising the Select Query II<br>
**Problem:** Query the NAME field for all American cities in the CITY table with populations larger than 120000. The CountryCode for America is USA.

**CITY**
| Field       | Type         |
|-------------|--------------|
| ID          | NUMBER       |
| NAME        | VARCHAR2(17) |
| COUNTRYCODE | VARCHAR2(3)  |
| DISTRICT    | VARCHAR2(20) |
| POPULATION  | NUMBER       |

**Solution:**
``` sql
SELECT NAME FROM city
WHERE countrycode = 'USA' AND population >= 120000;
```
<br>

**Topic:** Select All<br>
**Problem:** Query all columns (attributes) for every row in the CITY table.

**CITY**
| Field       | Type         |
|-------------|--------------|
| ID          | NUMBER       |
| NAME        | VARCHAR2(17) |
| COUNTRYCODE | VARCHAR2(3)  |
| DISTRICT    | VARCHAR2(20) |
| POPULATION  | NUMBER       |

**Solution:**
``` sql
SELECT * FROM city;
```
<br>

**Topic:** Select By ID<br>
**Problem:** Query all columns (attributes) for every row in the CITY table.

**CITY**
| Field       | Type         |
|-------------|--------------|
| ID          | NUMBER       |
| NAME        | VARCHAR2(17) |
| COUNTRYCODE | VARCHAR2(3)  |
| DISTRICT    | VARCHAR2(20) |
| POPULATION  | NUMBER       |

**Solution:**
``` sql
SELECT * FROM city WHERE id = "1661";
```
<br>

**Topic:** Japanese Cities' Attributes<br>
**Problem:** Query all attributes of every Japanese city in the CITY table. The COUNTRYCODE for Japan is JPN.

**CITY**
| Field       | Type         |
|-------------|--------------|
| ID          | NUMBER       |
| NAME        | VARCHAR2(17) |
| COUNTRYCODE | VARCHAR2(3)  |
| DISTRICT    | VARCHAR2(20) |
| POPULATION  | NUMBER       |

**Solution:**
``` sql
SELECT * FROM city WHERE countrycode = 'JPN';
```
<br>

**Topic:** Japanese Cities' Names<br>
**Problem:** Query the names of all the Japanese cities in the CITY table. The COUNTRYCODE for Japan is JPN.

**CITY**
| Field       | Type         |
|-------------|--------------|
| ID          | NUMBER       |
| NAME        | VARCHAR2(17) |
| COUNTRYCODE | VARCHAR2(3)  |
| DISTRICT    | VARCHAR2(20) |
| POPULATION  | NUMBER       |

**Solution:**
``` sql
SELECT NAME FROM city WHERE countrycode = 'JPN'
```
<br>

**Topic:** Weather Observation Station 1<br>
**Problem:** Query a list of CITY and STATE from the STATION table.

**CITY**
| Field       | Type         |
|-------------|--------------|
| ID          | NUMBER       |
| CITY        | VARCHAR2(21) |
| STATE       | VARCHAR2(2)  |
| LAT_N       | NUMBER       |
| LONG_W      | NUMBER       |

**Solution:**
``` sql
SELECT city, state FROM station;
```
<br>

**Topic:** Weather Observation Station 3<br>
**Problem:** Query a list of CITY names from STATION for cities that have an even ID number. Print the results in any order, but exclude duplicates from the answer.

**CITY**
| Field       | Type         |
|-------------|--------------|
| ID          | NUMBER       |
| CITY        | VARCHAR2(21) |
| STATE       | VARCHAR2(2)  |
| LAT_N       | NUMBER       |
| LONG_W      | NUMBER       |

**Solution:**
``` sql
SELECT DISTINCT city FROM station WHERE id % 2 = 0;
```
<br>

**Understanding:** I used modulo operator to check if the value for the ID will be even.
<br>

**Topic:** Weather Observation Station 4<br>
**Problem:** Find the difference between the total number of CITY entries in the table and the number of distinct CITY entries in the table.

**CITY**
| Field       | Type         |
|-------------|--------------|
| ID          | NUMBER       |
| CITY        | VARCHAR2(21) |
| STATE       | VARCHAR2(2)  |
| LAT_N       | NUMBER       |
| LONG_W      | NUMBER       |

**Solution:**
``` sql
SELECT COUNT(city) - COUNT(DISTINCT city) FROM station;
```
<br>

**Topic:** Weather Observation Station 5<br>
**Problem:** Query the two cities in STATION with the shortest and longest CITY names, as well as their respective lengths (i.e.: number of characters in the name). If there is more than one smallest or largest city, choose the one that comes first when ordered alphabetically.

**CITY**
| Field       | Type         |
|-------------|--------------|
| ID          | NUMBER       |
| CITY        | VARCHAR2(21) |
| STATE       | VARCHAR2(2)  |
| LAT_N       | NUMBER       |
| LONG_W      | NUMBER       |

**Solution:**
``` sql
SELECT DISTINCT city, LENGTH(city) FROM station
ORDER BY LENGTH(city) ASC, city ASC LIMIT 1;

SELECT DISTINCT city, LENGTH(city) FROM station
ORDER BY LENGTH(city) DESC, city ASC LIMIT 1;
```
<br>

**Understanding:** I created separate two queries; The first one is for listing the city in an ascending order where it will show the shortest city name while the second one is for the descending order which will show the longest city name.
<br>

**Topic:** Weather Observation Station 6<br>
**Problem:** Query the list of CITY names starting with vowels (i.e., a, e, i, o, or u) from STATION. Your result cannot contain duplicates.

**CITY**
| Field       | Type         |
|-------------|--------------|
| ID          | NUMBER       |
| CITY        | VARCHAR2(21) |
| STATE       | VARCHAR2(2)  |
| LAT_N       | NUMBER       |
| LONG_W      | NUMBER       |

**Solution:**
``` sql
SELECT DISTINCT city
FROM station
WHERE city LIKE 'a%' OR
city LIKE 'e%' OR
city LIKE 'i%' OR
city LIKE 'o%' OR
city LIKE 'u%' 
ORDER BY city ASC; 
```
<br>

**Understanding:** I used the OR logical operator to find the city names that starts with the vowels (a,e,i,o,u).
<br>

**Topic:** Weather Observation Station 7<br>
**Problem:** Query the list of CITY names ending with vowels (a, e, i, o, u) from STATION. Your result cannot contain duplicates.

**CITY**
| Field       | Type         |
|-------------|--------------|
| ID          | NUMBER       |
| CITY        | VARCHAR2(21) |
| STATE       | VARCHAR2(2)  |
| LAT_N       | NUMBER       |
| LONG_W      | NUMBER       |

**Solution:**
``` sql
SELECT DISTINCT city
FROM station
WHERE city LIKE '%a' OR
city LIKE '%e' OR
city LIKE '%i' OR
city LIKE '%o' OR
city LIKE '%u' 
ORDER BY city ASC; 
```
<br>

**Topic:** Weather Observation Station 8<br>
**Problem:** Query the list of CITY names from STATION which have vowels (i.e., a, e, i, o, and u) as both their first and last characters. Your result cannot contain duplicates.

**CITY**
| Field       | Type         |
|-------------|--------------|
| ID          | NUMBER       |
| CITY        | VARCHAR2(21) |
| STATE       | VARCHAR2(2)  |
| LAT_N       | NUMBER       |
| LONG_W      | NUMBER       |

**Solution:**
``` sql
SELECT DISTINCT city
FROM station
WHERE LEFT(city,1)
IN ('a', 'e', 'i', 'o', 'u')
AND RIGHT(city,1) IN ('a', 'e', 'i', 'o', 'u') 
ORDER BY city ASC; 
```
<br>

**Understanding:** For this one, instead of using the OR logical operator, I shorten it up by using the LEFT and RIGHT functions to check the first and last letter of the city names if it contains vowels by using the IN function. Then I used the AND logical operator to comply with the problem requirement.
<br>

**Topic:** Weather Observation Station 9<br>
**Problem:** Query the list of CITY names from STATION that do not start with vowels. Your result cannot contain duplicates.

**CITY**
| Field       | Type         |
|-------------|--------------|
| ID          | NUMBER       |
| CITY        | VARCHAR2(21) |
| STATE       | VARCHAR2(2)  |
| LAT_N       | NUMBER       |
| LONG_W      | NUMBER       |

**Solution:**
``` sql
SELECT DISTINCT city
FROM station
WHERE LEFT(city,1) NOT IN ('a', 'e', 'i', 'o', 'u')
ORDER BY city ASC;
```
<br>

**Topic:** Weather Observation Station 10<br>
**Problem:** Query the list of CITY names from STATION that do not end with vowels. Your result cannot contain duplicates.

**CITY**
| Field       | Type         |
|-------------|--------------|
| ID          | NUMBER       |
| CITY        | VARCHAR2(21) |
| STATE       | VARCHAR2(2)  |
| LAT_N       | NUMBER       |
| LONG_W      | NUMBER       |

**Solution:**
``` sql
SELECT DISTINCT city
FROM station
WHERE RIGHT(city,1) NOT IN ('a', 'e', 'i', 'o', 'u')
ORDER BY city ASC;
```
<br>

**Topic:** Weather Observation Station 11<br>
**Problem:** Query the list of CITY names from STATION that either do not start with vowels or do not end with vowels. Your result cannot contain duplicates.

**CITY**
| Field       | Type         |
|-------------|--------------|
| ID          | NUMBER       |
| CITY        | VARCHAR2(21) |
| STATE       | VARCHAR2(2)  |
| LAT_N       | NUMBER       |
| LONG_W      | NUMBER       |

**Solution:**
``` sql
SELECT DISTINCT city
FROM station
WHERE LEFT(city,1)
NOT IN ('a', 'e', 'i', 'o', 'u')
OR RIGHT(city,1) NOT IN ('a', 'e', 'i', 'o', 'u') 
ORDER BY city ASC; 
```
<br>

**Topic:** Weather Observation Station 12<br>
**Problem:** Query the list of CITY names from STATION that do not start with vowels and do not end with vowels. Your result cannot contain duplicates.

**CITY**
| Field       | Type         |
|-------------|--------------|
| ID          | NUMBER       |
| CITY        | VARCHAR2(21) |
| STATE       | VARCHAR2(2)  |
| LAT_N       | NUMBER       |
| LONG_W      | NUMBER       |

**Solution:**
``` sql
SELECT DISTINCT city
FROM station
WHERE LEFT(city,1)
NOT IN ('a', 'e', 'i', 'o', 'u')
AND RIGHT(city,1) NOT IN ('a', 'e', 'i', 'o', 'u') 
ORDER BY city ASC; 
```
<br>

**Topic:** Higher Than 75 Marks<br>
**Problem:** Query the Name of any student in STUDENTS who scored higher than 75 Marks. Order your output by the last three characters of each name. If two or more students both have names ending in the same last three characters (i.e.: Bobby, Robby, etc.), secondary sort them by ascending ID.

**STUDENTS**
| Field       | Type         |
|-------------|--------------|
| ID          | INTEGER      |
| NAME        | STRING       |
| MARKS       | INTEGER      |

**Solution:**
``` sql
SELECT name
FROM students
WHERE marks > '75'
ORDER BY RIGHT(name,3), ID ASC;
```
<br>

**Understanding:** I used the RIGHT function to check the last 3 letters/characters of the name of the students and also sorted them out by using the ASC keyword.<br>

**Topic:** Employee Names<br>
**Problem:** Write a query that prints a list of employee names (i.e.: the name attribute) from the Employee table in alphabetical order.

**EMPLOYEE**
| Column        | Type         |
|---------------|--------------|
| employee_id   | Integer      |
| name          | String       |
| months        | Integer      |
| salary        | Integer      |

**Solution:**
``` sql
SELECT name
FROM employee
ORDER BY name ASC;
```
<br>

**Topic:** Employee Salaries<br>
**Problem:** Write a query that prints a list of employee names (i.e.: the name attribute) for employees in Employee having a salary greater than 2000 per month who have been employees for less than 10 months. Sort your result by ascending employee_id.

**EMPLOYEE**
| Column        | Type         |
|---------------|--------------|
| employee_id   | Integer      |
| name          | String       |
| months        | Integer      |
| salary        | Integer      |

**Solution:**
``` sql
SELECT name
FROM employee
WHERE salary > '2000' AND months < 10
ORDER BY employee_id ASC;
```