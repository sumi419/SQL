SQL, or Structured Query Language, is a language designed to allow both technical and non - technical users query, manipulate, and transform data from a relational database.

### SQL Lesson 1: SELECT queries 101 ###
#### Select query for a specific columns ####
*SELECT column, another_column, …
FROM mytable;*

#### Select query for all columns ####
*SELECT * 
FROM mytable;*

1.SELECT title FROM movies; *(Select query for a specific columns)*

2.SELECT director FROM movies;

3.SELECT title, director FROM movies;

4.SELECT title, year FROM movies;

5.SELECT * FROM movies; *(Select query for all columns)*


### SQL Lesson 2: Queries with constraints (Pt. 1) ###
#### Select query with constraints ####
*SELECT column, another_column, …
FROM mytable
WHERE condition
    AND/OR another_condition
    AND/OR …;*

1.SELECT id, title FROM movies 
WHERE id = 6;

2.SELECT title, year FROM movies
WHERE year BETWEEN 2000 AND 2010;

3.SELECT title, year FROM movies
WHERE year NOT BETWEEN 2000 AND 2010;

SELECT title, year FROM movies
WHERE year < 2000 OR year > 2010;

4.SELECT * FROM movies
WHERE id between 1 and 5;

SELECT title, year FROM movies
WHERE year <= 2003;

### SQL Lesson 3: Queries with constraints (Pt. 2) ###
#### Select query with constraints ####
*SELECT column, another_column, …
FROM mytable
WHERE condition
    AND/OR another_condition
    AND/OR …;*

1.SELECT * FROM movies where title like "%toy story%";

SELECT title, director FROM movies 
WHERE title LIKE "Toy Story%";

2.SELECT title, director FROM movies 
WHERE director = "John Lasseter";

3.SELECT title, director FROM movies 
WHERE director != "John Lasseter";

4.SELECT title, director FROM movies 
WHERE title like "%Wall-%";

SELECT * FROM movies 
WHERE title LIKE "WALL-_";

### SQL Lesson 4: Filtering and sorting Query results ###
#### Select query with unique results ####

*SELECT DISTINCT column, another_column, …
FROM mytable
WHERE condition(s);*
(distinct removes duplicate rows)

#### Select query with ordered results ####
*SELECT column, another_column, …
FROM mytable
WHERE condition(s)
ORDER BY column ASC/DESC;*

#### Limiting results to a subset(Limiting results to a subset) ####
*SELECT column, another_column, …
FROM mytable
WHERE condition(s)
ORDER BY column ASC/DESC
LIMIT num_limit OFFSET num_offset;*
*The LIMIT will reduce the number of rows to return, and the optional OFFSET will specify where to begin counting the number rows from.*  
(offset will start from the number you set it ahead by, for example if you want to start counting from the next 5 you would OFFSET 5)

1.SELECT DISTINCT director FROM movies
ORDER BY director ASC;

2.List the last four Pixar movies released (ordered from most recent to least)  
SELECT title, year FROM movies
ORDER BY year DESC
LIMIT 4;

3.List the first five Pixar movies sorted alphabetically  
SELECT title FROM movies
ORDER BY title ASC
LIMIT 5;

4.List the next five Pixar movies sorted alphabetically  
SELECT title FROM movies
ORDER BY title ASC
LIMIT 5 OFFSET 5;

### SQL Lesson 5 Review: Simple SELECT Queries ###
SELECT query  
*SELECT column, another_column, …
FROM mytable
WHERE condition(s)
ORDER BY column ASC/DESC
LIMIT num_limit OFFSET num_offset;*

1.SELECT city, population FROM north_american_cities
WHERE country = "Canada";

2.SELECT city, latitude FROM north_american_cities
WHERE country = "United States"
ORDER BY latitude DESC;

3.SELECT city, longitude FROM north_american_cities
WHERE longitude < -87.629798
ORDER BY longitude ASC;

3.List the two largest cities in Mexico (by population)  
more than 2 search results, use limit 2  
SELECT city, population FROM north_american_cities
WHERE country LIKE "Mexico"
ORDER BY population DESC
LIMIT 2;

4.List the third and fourth largest cities (by population) in the United States and their population  
must offset the search by two values so it starts from the 3rd largest instead of the first largest city  
SELECT city, population FROM north_american_cities
WHERE country LIKE "United States"
ORDER BY population DESC
LIMIT 2 OFFSET 2;

### SQL Lesson 6: Multi-table queries with JOINs ###
#### Select query with INNER JOIN on multiple tables ####
*SELECT column, another_table_column, …
FROM mytable
INNER JOIN another_table 
    ON mytable.id = another_table.id
WHERE condition(s)
ORDER BY column, … ASC/DESC
LIMIT num_limit OFFSET num_offset;*

primary key type is an auto-incrementing integer that's unique  
The INNER JOIN is a process that matches rows from the first table and the second table which have the same key

1.SELECT title, domestic_sales, international_sales 
FROM movies
  JOIN boxoffice
    ON movies.id = boxoffice.movie_id;

2.SELECT title, domestic_sales, international_sales
FROM movies
  JOIN boxoffice
    ON movies.id = boxoffice.movie_id
WHERE international_sales > domestic_sales;

3.SELECT title, rating
FROM movies
  JOIN boxoffice
    ON movies.id = boxoffice.movie_id
ORDER BY rating DESC;

### SQL Lesson 7: OUTER JOINs ###
#### Select query with LEFT/RIGHT/FULL JOINs on multiple tables ####
*SELECT column, another_column, …
FROM mytable
INNER/LEFT/RIGHT/FULL JOIN another_table 
    ON mytable.id = another_table.matching_id
WHERE condition(s)
ORDER BY column, … ASC/DESC
LIMIT num_limit OFFSET num_offset;*

1.SELECT DISTINCT building FROM employees;

2.SELECT * FROM buildings;

3.SELECT DISTINCT building_name, role 
FROM buildings 
  LEFT JOIN employees
    ON building_name = building;

LEFT JOIN simply includes rows from table A regardless of whether a matching row is found in B.  
RIGHT JOIN is the same, but reversed, keeping rows in B regardless of whether a match is found in A.  
FULL JOIN simply means that rows from both tables are kept, regardless of whether a matching row exists in the other table.  

### SQL Lesson 8: A short note on NULLs ###
#### Select query with constraints on NULL values ####