## SQL Questions

First create a database called fringe_shows
```
  #terminal
  psql
  create database fringe_shows;
  \q
```

Populate the data using the script - fringeshows.sql
```
  #terminal
  psql -d fringe_shows -f fringeshows.sql
```

Using the SQL Database file given to you as the source of data to answer the questions.  Copy the SQL command you have used to get the answer, and paste it below the question, along with the result they gave.



## Section 1

  This section involves more complex queries.  You will need to go and find out about aggregate functions in SQL to answer some of the next questions.

  1. Select the names and prices of all shows, ordered by price in ascending order.
  '''
  SELECT price, name FROM shows ORDER BY price;
  '''

  10. Select the average price of all shows.
  '''
  SELECT AVG(price) FROM shows;
  '''

  11. Select the price of the least expensive show.
  '''
  SELECT MIN(price) FROM shows;
  '''

  12. Select the sum of the price of all shows.
  '''
  SELECT SUM(price) FROM shows;
  '''

  13. Select the sum of the price of all shows whose prices is less than £20.
  '''
  SELECT SUM(price) FROM shows WHERE price < 20.00;
  '''

  14. Select the name and price of the most expensive show.
  '''
  SELECT name, price FROM shows WHERE price = (SELECT MAX(price) FROM shows);
  '''

  15. Select the name and price of the second from cheapest show.
  '''
  SELECT name, price FROM shows WHERE price > (SELECT min(price) FROM shows) ORDER BY price ASC LIMIT 1;
  '''

  16. Select the names of all users whose names start with the letter "M".
  '''
  SELECT * FROM users WHERE name LIKE 'M%';
  '''

  17. Select the names of users whose names contain "er".
  '''
  SELECT * FROM users WHERE name LIKE '%er%';
  '''


## Section 2

  The following questions can be answered by using nested SQL statements but ideally you should learn about JOIN clauses to answer them.

  10. Select the time for the Edinburgh Royal Tattoo.


  SELECT created_at FROM shows WHERE name = ('Edinburgh Royal Tattoo')
  UNION ALL
  SELECT CONVERT (varchar(10), sysdate, 108);

  19. Select the number of users who want to see "Shitfaced Shakespeare".

  20. Select all of the user names and the count of shows they're going to see.

  21. SELECT all users who are going to a show at 17:15.
