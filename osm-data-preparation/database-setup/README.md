# Lesson 4. Database setup

PostgreSQL is a popular open-source relational database management system (RDBMS) that provides powerful tools for storing, querying, and managing large datasets. It is widely used in web applications and provides strong support for handling geospatial data, making it an ideal choice for storing and managing OpenStreetMap (OSM) data.

## Task

In this lesson, we will go through the process of setting up a PostgreSQL database. The first step is to download and install PostgreSQL on your computer, which can be done by following the instructions provided on [the PostgreSQL website](https://www.postgresql.org/download/) for your operating system.

Once PostgreSQL is installed, we need to create a new database. This can be done in the pgAdmin (installed with PostgreSQL). 

Open it, set the master password and register new server. You must type in your server's host name (localhost) and your password.

After that, you will get an access to the PostgreSQL system database. We should create new database (click Databases -> Create -> Database), name it `geodb`.

Then make a report with screenshots of your new database in pgAdmin and commit it.