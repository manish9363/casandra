## Data Modeling with Apache Cassandra

## Introduction:
The purpose of this project is to create an Apache Cassandra database for a ficticious startup called Sparkify to query on song play data. The raw data is in a directory of CSV files, and we will build a ETL pipeline to transform the raw data into the Apache Cassandra database.

## Dataset
    artist (string)
    auth (string)
    firstName (string)
    gender (char)
    itemInSession (int)
    lastName (string)
    length (float)
    level (string)
    location (string)
    method (string)
    page (string)
    registration (float)
    sessionId (int)
    song (string)
    status (int)
    ts (float)
    userId (int)

## Requirement for all the use cases are listed below:
    
usecase 1 (Query1):
    Find artist, song title and song length that was heard during sessionId=338, and itemInSession=4.
    SELECT artist, song, length from table_1 WHERE sessionId=338 AND itemInSession=4
    
usecase 2 (Query 2):
    Find name of artist, song (sorted by itemInSession) and user (first and last name) for userid=10, sessionId=182.
    SELECT artist, song, firstName, lastName FROM table_2 WHERE userId=10 and sessionId=182
    
usecase 3(Query 3):    
    Find every user name (first and last) who listened to the song 'All Hands Against His Own'.
    SELECT firstName, lastName WHERE song='All Hands Againgst His Own'



Query 1 table details :
    
Column 1 = sessionId
Column 2 = itemInSession
Column 3 = artist
Column 4 = song
Column 5 = length
Primary key = (sessionId, itemInSession)


query 2 table details:
    
Column 1 = userId
Column 2 = sessionId
Column 3 = artist
Column 4 = song
Column 5 = itemInSession
Column 6 = firstName
Column 7 = lastName
Primary key = (userId, sessionId) with clustering column itemInSession

Query 3 table details:
    
Column 1 = song
Column 2 = firstName
Column 3 = lastName
Primary key = (song)
    
## ETL Pipeline

Step 1: select raw data user file from file server , here it will be folder location.
Step 2 : there will be 3 sets for create table , insert table and query. 
Step 3 : create table and select the data element from the file for each use case
step 4 : partition is very inportant aspect of the table. based on where clause  define the partition column.; 
step 5 : run the job in python notenook . 


## 
