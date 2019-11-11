# Project Sparkify

## Purpose

Sparkify, a startup is analyzing data being collected on songs and user activity.
In particular understanding what songs users have been listening to.

## Schema Design

The following fact and dimension tables have been created for analytical purposes:

### Dimension Tables

- **users:** users in the app
- **songs:** songs in the music database
- **artists:** artists in the music database
- **time:** timestamps of records in *songplays* broken down into specific units

### Fact Table

- **songplays:** records in data associated with song plays



## ETL Pipeline

An ETL Pipeline was created to extract data from json log files and insert into database tables shown above.
Steps are below:

- functions for processing log and song files: Functions have been created to extract data from both json files (log/song).
    Contained within the function is reading contents of file, inserting record into table.
- process data function: this function is responsible for iterating over all files and using the `process_log/process_song`
    functions.
- finally in `main`: In the `main` process:
    - connection is made to database
    - `process_data` function is impletemented (see above for details on this function)
    - connection is closed