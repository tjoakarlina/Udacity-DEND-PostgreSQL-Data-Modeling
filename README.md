# Project: Data Modeling with PostgreSQL


## Background
A startup called Sparkify wants to analyze the data they've been collecting on songs and user activity on their new music streaming app. The analytics team is particularly interested in understanding what songs users are listening to. Currently, they don't have an easy way to query their data, which resides in a directory of JSON logs on user activity on the app, as well as a directory with JSON metadata on the songs in their app.

The objective of the projects are:
- Create a database schema
- Create a Postgres database with tables designed to optimize queries on songplay analysis
- Create an ETL pipeline to feed the data from the user longs and songs files.


## Explanation of Files in the Repository


### Data Set
There are two data set that we will feed to the database:


#### Song dataset
Song dataset is a collection of json files where each of the file contain the description of a song. These are the information stored in the song file:
1. num_songs
2. artist_id
3. artist_latitude
4. artist_location
5. artist_name
6. song_id
7. title
8. duration
9. year


#### User Event Log
User Event Log is a collection of json files which stores the user activity log while interacting with Sparkify website/application. Each file contains activity logs for Sparkify users on a given day.
Each activity log contains the following information:
1. artist
2. auth
3. firstName
4. lastName
5. gender
6. itemInSession
7. length
8. level
9. location
10. method
11. page
12. registration
13. sessionId
14. song
15. status
16. ts
17. userAgent
18. userId


### Jupyter Notebook Files
There are two jupyter notebook files that were created for experimentation:
1. etl.ipynb - to experiment with loading the dataset file to the PostgreSQL tables
2. test.ipynb - to test whether the table and the data are correct after we perform the ETL


### Python Scripts
1. sql_queries.py - list all the SQL queries needed for the projects, which includes table creations, table insertions, retrieving data from table, and dropping the table.
2. create_tables.py - drop the existing tables if exist and create empty tables
3. etl.py - run the ETL to load data to the tables


## Get Started
Please follow these steps to set up the database and execute the ETL pipeline:

1. Run the postgres student image which is provided in the following [link](https://hub.docker.com/r/onekenken/postgres-student-image):
```commandline
docker run -d --name postgres-student-container -p 5432:5432 onekenken/postgres-student-image
```
This command will bring up a postgreSQL database in a docker container, which is accessible via localhost port 5432.

3. Setup the database and tables. Please run the following command
```commandline
python create_tables.py
```

3. Run the ETL pipeline to read the data files and load them to the database. Please run the following command
```commandline
python etl.py
```