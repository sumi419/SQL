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
####Select query with constraints####
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