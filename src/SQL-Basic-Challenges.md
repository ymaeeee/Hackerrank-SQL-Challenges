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
SELECT * FROM CITY
WHERE COUNTRYCODE = 'USA' AND POPULATION >= 100000;
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
SELECT NAME FROM CITY
WHERE COUNTRYCODE = 'USA' AND POPULATION >= 120000;
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
SELECT * FROM CITY;
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
SELECT * FROM CITY WHERE ID = "1661";
```