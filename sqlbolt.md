SQL, or Structured Query Language, is a language designed to allow both technical and non - technical users query, manipulate, and transform data from a relational database.

### SQL Lesson 1: SELECT queries 101 ###
1.SELECT title FROM movies; *(Select query for a specific columns)*
2.SELECT director FROM movies;
3.SELECT title, director FROM movies;
4.SELECT title, year FROM movies;
5.SELECT * FROM movies; *(Select query for all columns)*


### SQL Lesson 2: Queries with constraints (Pt. 1) ###
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
WHERE year NOT BETWEEN 2000 AND 2010;0
SELECT title, year FROM movies
WHERE year < 2000 OR year > 2010;
4.SELECT * FROM movies
WHERE id between 1 and 5;
SELECT title, year FROM movies
WHERE year <= 2003;