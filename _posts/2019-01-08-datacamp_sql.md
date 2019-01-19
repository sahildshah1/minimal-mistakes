---
published: true
title: "Notes from DataCamp's SQL courses"
---

Here are the notes I took when I was learing new [SQL skills on DataCamp](https://www.datacamp.com/courses/tech:sql)

## Intro to SQL for Data Science

Course Objective: Know how to begin wrangling and extracting data from
relational databases (organized collections of tables) using (Postgre)SQL

### Selecting columns

- A query is a request for data from a database table. Select data from a table using a SELECT statement. Select all the unique values from a column, you can use the DISTINCT keyword.

- COUNT(*): number of rows in the table, e.g. COUNT(birthdate): *number
of non-missing values*, e.g. COUNT(DISTINCT birthdate): number of distinct
values in the column  


### Filtering rows

- WHERE keyword allows you to filter based on both text and numeric values in a table. *PostgreSQL uses single ‘‘  not double ““ *

- BETWEEN keyword provides a useful shorthand for filtering values within a specified range. e.g. WHERE release_year BETWEEN 1990 AND 2000. *BETWEEN is inclusive*

-  IN operator allows you to specify multiple values in a WHERE clause. e.g.
WHERE age IN (2, 4, 6, 8, 10); WHERE release_year NOT IN (2015)

- the LIKE operator can be used in a WHERE clause to search for a pattern in a column. ** % wildcard will match zero, one, or many characters in text.*
* The _ wildcard will match a single character*  e.g. title LIKE 'A%'

### Aggregate functions

- SQL assumes that if you divide an integer by an integer, you want to get an integer back. So be careful when dividing! e.g. 4/3 = 1
If you want more precision when dividing, you can add decimal places to your number  4.0/3.0 = 1.33

<!-- 
AVG(duration)/60.0 vs AVG(duration/60)? Are they the same?
COUNT(deathdate) * 100.0 / COUNT(*)
COUNT deathdate NULL?  -->


### Sorting, grouping and joins


- ORDER BY keyword is used to sort results in ascending or descending order according to the values of one or more columns. It will sort by the first column specified, then sort by the next, then the next, and so on. *Order of columns is important!* 

- If you want to sort the results in descending order, you can use the DESC keyword. e.g. ORDER BY name DESC;

- GROUP BY allows you to group a result by one or more columns. **SELECT columns you want to use in GROUP BY clause**. The column's that are not in GROUP BY clause should be used to calculate some kind of value (e.g. COUNT(), MAX()) or SQL will return an error. e.g. SELECT language, SUM(gross) FROM films GROUP BY language


-  Note that ORDER by always goes after GROUP BY. Make sure to always put the ORDER BY clause at the end of your query. You can't sort values that you haven't calculated yet!


<!-- 
SELECT release_year, country, MAX(budget)
FROM films
GROUP BY release_year, country
ORDER BY release_year, country ?? -->

- If you want to filter based on the result of an aggregate function, you need another way! That's where the HAVING clause comes in. e.g. HAVING COUNT(title) > 10;


<!-- SELECT release_year
FROM films
WHERE release_year > 1990
GROUP BY release_year

GROUP BY without calculating some kind of value \implies Distinct release years?

if the average budget is greater than $60 million.
HAVING AVG(budget) > 60000000


HAVING COUNT(country) > 10

WHERE on aggregate functions using HAVING
 -->


## Joining Data in SQL

