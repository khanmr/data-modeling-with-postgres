## Project: Data Modeling with Postgres

### Summary

This project uses data from Sparkify, a music streaming app, and models user activity with a Postgres database and ETL pipeline using Python and SQL. The goal is to help the analytics team identify the songs users are listening to.

### Database Schema

A star schema was used to design the database to optimize queries on song play analysis. An ETL pipeline using Python and SQL will extract the data from the song and log datasets to a Postgres database. Below are the tables included in the database schema:

**Fact Table**
**songplays** - records in log data associated with song plays i.e. records with page `NextSong`
- songplay_id, start_time, user_id, level, song_id, artist_id, session_id, location, user_agent

**Dimension Tables**
**users** - users in the app
- user_id, first_name, last_name, gender, level

**songs** - songs in music database
- song_id, title, artist_id, year, duration

**artists** - artists in music database
- artist_id, name, location, latitude, longitude

**time** - timestamps of records in songplays broken down into specific units
- start_time, hour, day, week, month, year, weekday

### Instructions

From the terminal, run the following commands to create tables and run ETL pipeline to process the datasets to the `sparkifydb` database:

```
python create_tables.py

python etl.py
```

Run `test.ipynb` to confirm records were successfully inserted into each table. Make sure to click "Restart kernel" to close the connection to the database after running notebook.

NOTE: To reset tables, run `create_tables.py` before running `etl.py`.
