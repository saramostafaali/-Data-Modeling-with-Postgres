
# Data Modeling with Postgres
# Introduction


A startup called Sparkify wants to analyze the data they've been collecting on songs and user activity on their new music streaming app. The analytics team is particularly interested in understanding what songs users are listening to, they need a Postgres database with tables designed to optimize queries on song play analysis.

# Project Description
-	For this analysis, I will define fact and dimension tables for a star schema for a particular analytic focus, and create ETL pipeline that transfers data from files in two local directories into these tables in Postgres using Python and SQL. 

-	I’ll be able to test the database and ETL pipeline by running queries given by the analytics team from Sparkify and compare my results with their expected results.

## Schema Design 
For Sparkify database i designed a star schema which consist of one fact table (songplays), and  four dimensional tables (songs, artists, users and time).

 ![Sparkify star schema](https://drive.google.com/file/d/1gJ2sLSXYSvRRhitleci_2q3YdNun6yyr/view?usp=sharing)

#### Fact Table
- songplays - records in log data associated with song plays i.e. records with page NextSong
  
  songplay_id, start_time, user_id, level, song_id, artist_id, session_id, location, user_agent


#### Dimension Tables
-	users - users in the app

     user_id, first_name, last_name, gender, level

-	songs - songs in music database

 	 song_id, title, artist_id, year, duration

-	artists - artists in music database

     artist_id, name, location, latitude, longitude

-	time - timestamps of records in songplays broken down into specific units
    
     start_time, hour, day, week, month, year, weekday

## Files in the repository
-	test.ipynb- displays the first few rows of each table to let you check your database.
-	create_tables.py- drops and creates your tables. You run this file to reset your tables before each time you run your ETL scripts.
-	etl.ipynb- reads and processes a single file from song_data and log_data and loads the data into your tables. This notebook contains detailed instructions on the ETL process for each of the tables.
-	etl.py- reads and processes files from song_data and log_data and loads them into your tables. You can fill this out based on your work in the ETL notebook.
-	sql_queries.py- contains all your sql queries, and is imported into the last three files above.
-	README.md- provides discussion on your project.
