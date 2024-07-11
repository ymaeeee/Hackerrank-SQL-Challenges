<h1> Hackerrank's SQL Advance Challenges </h1>

## File Description
<p> This markdown file contains the advance SQL challenges from Hackerrank that I have solved. Feel free to check my solutions and understanding for each problems.</p>

### SQL Challenges/Problems

**Topic:** Type of Triangle<br>
**Problem:** Write a query identifying the type of each record in the TRIANGLES table using its three side lengths. Output one of the following statements for each record in the table:

Equilateral: It's a triangle with 3 sides of equal length.
Isosceles: It's a triangle with 2 sides of equal length.
Scalene: It's a triangle with 3 sides of differing lengths.
Not A Triangle: The given values of A, B, and C don't form a triangle.

**TRIANGLE**
| Column  | Type    | 
|---------|---------|
| A       | INTEGER |
| B       | INTEGER |
| C       | INTEGER |

**Solution:**
``` sql
SELECT 
CASE
    WHEN ( A + B ) <= C OR ( A + C ) <= B OR ( B + C ) <= A THEN 'Not A Triangle'
    WHEN A = B AND B = C AND A = C THEN ' Equilateral'
    WHEN A = B OR B = A OR A = C OR B = C THEN 'Isosceles'
    ELSE 'Scalene'
END
FROM triangles;
```
<br>

**Understanding:** I first created a case to check if the given values for A, B, and C will be possible to form a triangle based on the triangle inequality theorem. To check this, I created conditions where in the sum of two sides shouldn't be larger than the other one. If it's true then it's print the "Not A Triangle" message. Once values for A, B, and C are proven that can form a triangle, in the next case, I checked if the 3 columns A, B, and C are all equal so it'll display the "Equilateral" message. Third case, I checked if any of the columns will be equal to one column, and if it will be true it will print the "Isosceles" message else the "Scalene" message will output if no sides are equal.