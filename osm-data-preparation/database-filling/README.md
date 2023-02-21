# Lesson 5. Database filling

## Using PostGIS and osm2psql tool

After creating the database, we need to enable the PostGIS extension that provides support for geospatial data types and functions in PostgreSQL. First, we need to download and install [PostGIS](https://postgis.net/install/). Second, we need to connect to the database using the psql command-line utility and run the following SQL command:

```
CREATE EXTENSION postgis;
```
With PostGIS enabled, we can now load OSM data into the database using the osm2pgsql tool, which is a popular tool for importing OSM data into PostgreSQL. This tool reads OSM data in various file formats, such as PBF, XML, and others, and converts it into a format that can be loaded into the PostgreSQL database.

After PostGIS installation, you must download [osm2pgsql](https://osm2pgsql.org/doc/install.html) tool. Then, use the following command (in terminal) to load OSM data into the geodb database:

```
osm2pgsql --create --database geodb --username postgres --password your-password path/to/osm/data.osm.pbf
```
This command will create a new PostgreSQL database schema, load the OSM data from the file data.osm.pbf, and store it in the geodb database using the postgres user.

After loading the data, we can perform various geospatial queries on the OSM data using the powerful PostGIS functions and tools, such as finding all restaurants within a certain radius or calculating the shortest path between two locations.

## Task

Create a database from your extracted file with use of `osm2pgsql`. Commit a report with screenshots of database (tables) in pgAdmin.

