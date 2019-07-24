1. Find all the robots from Star Wars.
intro_to_sql=# SELECT * FROM robots WHERE source = 'Star Wars'
intro_to_sql-# ;
 name |  source   | personality | id 
------+-----------+-------------+----
 C3PO | Star Wars | anxious     |  4
 R2D2 | Star Wars | loyal       |  8
(2 rows)

2. Find the robot with an "anxious" personality.
intro_to_sql=# SELECT * FROM robots WHERE personality = 'anxious';
 name |  source   | personality | id 
------+-----------+-------------+----
 C3PO | Star Wars | anxious     |  4
(1 row)

3. Find all recipes that are nut free.
intro_to_sql=# SELECT name FROM recipes WHERE nut_free = True;
                   name                    
-------------------------------------------
 Butternut Squash Bake
 Vegetarian Bibimbap
 French Veggie Loaf
 Quinoa and Black Beans
 Juicy Roasted Chicken
 Garlic Green Beans
 Stout Slow Cooker Corned Beef and Veggies
(7 rows)

4. Count the number of recipes that are gluten free but not vegetarian.
intro_to_sql=# SELECT COUNT(gluten_free) FROM recipes WHERE vegetarian = False;
 count 
-------
     2
(1 row)

5. Find the animal with the most legs.
intro_to_sql=# SELECT MAX(number_of_legs) FROM animals;
 max 
-----
   8
(1 row)

intro_to_sql=# SELECT * FROM animals WHERE number_of_legs = 8;
  name   | number_of_legs | flying | swimming | egg_laying | id 
---------+----------------+--------+----------+------------+----
 octopus |              8 | f      | t        | t          |  3
(1 row)

6. Find the board game that takes the least amount of time to play.
intro_to_sql=# SELECT MIN(mins_to_play) FROM board_games;
 min 
-----
  15
(1 row)

intro_to_sql=# SELECT * FROM board_games WHERE mins_to_play = 15;
   name   | max_players | min_players | category | mins_to_play | id 
----------+-------------+-------------+----------+--------------+----
 Sushi Go |           5 |           2 | party    |           15 | 10
 Quixo    |           4 |           2 | abstract |           15 | 11
(2 rows)

7. Find the recipe that takes the most time to prepare.

intro_to_sql=# SELECT MAX(minutes_required) FROM recipes;
 max 
-----
 390
(1 row)
intro_to_sql=# SELECT name  FROM recipes WHERE minutes_required = 390;
                   name                    
-------------------------------------------
 Stout Slow Cooker Corned Beef and Veggies
(1 row)


8. Find all the robots whose name starts with the letter M.
intro_to_sql=# SELECT * FROM robots WHERE name LIKE 'M%'
intro_to_sql-# ;
      name      |                source                |  personality  | id 
----------------+--------------------------------------+---------------+----
 Marvin         | The Hitchhiker's Guide to the Galaxy | pessimistic   |  3
 Mr. Butlertron | Clone High                           | compassionate |  5
(2 rows)

9. Count the number of board games that can be played by 8 people.

intro_to_sql=# SELECT * FROM board_games WHERE max_players >= 8;
          name          | max_players | min_players | category | mins_to_play | id 
------------------------+-------------+-------------+----------+--------------+----
 Arkham Horror          |           8 |           1 | strategy |          240 |  1
 Cards Against Humanity |          30 |           5 | party    |           30 |  8
 Game of Things         |          15 |           2 | party    |           45 |  9
(3 rows)

10. Find all animals that are swimming and egg-laying. 
intro_to_sql=# SELECT * FROM animals WHERE swimming = True AND egg_laying = True;
  name   | number_of_legs | flying | swimming | egg_laying | id 
---------+----------------+--------+----------+------------+----
 octopus |              8 | f      | t        | t          |  3
 duck    |              2 | t      | t        | t          |  4
(2 rows)

11.   Find all animals that are swimming and egg-laying but not flying.
intro_to_sql=# SELECT * FROM animals WHERE swimming = True AND egg_laying = True AND flying = False; 
  name   | number_of_legs | flying | swimming | egg_laying | id 
---------+----------------+--------+----------+------------+----
 octopus |              8 | f      | t        | t          |  3
(1 row)

12. Find the board game that supports the largest number of people.
intro_to_sql=# SELECT MAX(max_players) FROM board_games;
 max 
-----
  30
(1 row)

intro_to_sql=# SELECT * FROM board_games WHERE max_players = 30;
          name          | max_players | min_players | category | mins_to_play | id 
------------------------+-------------+-------------+----------+--------------+----
 Cards Against Humanity |          30 |           5 | party    |           30 |  8
(1 row)

