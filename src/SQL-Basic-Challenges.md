<h1> Hackerrank's SQL Basic Challenges </h1>

## Folder Description
<p> This markdown file contains the basic SQL challenges from Hackerrank that I have solved. Feel free to check my solutions for each problems.</p>

### SQL Challenges/Problems

**Topic:** Revising the Select Query I
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