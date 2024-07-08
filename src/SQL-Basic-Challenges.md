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
**Understanding:** I created separate two queries/; The first one is for listing the city in an ascending order where it will show the shortest city while the second one is for the descending order which will show the longest city name.
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
