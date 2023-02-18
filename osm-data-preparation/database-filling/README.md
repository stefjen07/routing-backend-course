# Lesson 5. Database filling

## Using PostGIS and osm2psql tool

After creating the database and user, we need to enable the PostGIS extension that provides support for geospatial data types and functions in PostgreSQL. This can be done by connecting to the database using the psql command-line utility and running the following SQL command:

```
CREATE EXTENSION postgis;
```
With PostGIS enabled, we can now load OSM data into the database using the osm2pgsql tool, which is a popular tool for importing OSM data into PostgreSQL. This tool reads OSM data in various file formats, such as PBF, XML, and others, and converts it into a format that can be loaded into the PostgreSQL database.

To load OSM data into the geodb database, we can use the following command:

```
osm2pgsql --create --database geodb --username geouser path/to/osm/data.osm.pbf
```
This command will create a new PostgreSQL database schema, load the OSM data from the file data.osm.pbf, and store it in the geodb database using the geouser user.

After loading the data, we can perform various geospatial queries on the OSM data using the powerful PostGIS functions and tools, such as finding all restaurants within a certain radius or calculating the shortest path between two locations.

## Using custom XML parser

But what if we don't want to use third-party database. 

OpenStreetMap (OSM) data can be parsed and loaded into a database from scratch using a combination of programming languages and tools. In this lesson, we will use Java and PostgreSQL to parse an OSM XML file and load it into a PostgreSQL database.

The first step is to download an OSM XML file that contains the desired OSM data. There are several ways to obtain OSM data, including downloading it from the OSM website or using a third-party service that provides OSM data. Once we have the XML file, we can start parsing it.

To parse the XML file, we can use a Java XML parser library such as javax.xml.stream, which is included in the Java standard library. This library provides an event-driven parsing model that allows us to iterate through the XML elements and extract the necessary data.

The next step is to create a database schema in PostgreSQL that matches the OSM data structure. This can be done using SQL commands that create tables with the necessary columns for storing the OSM data. For example, we might create a nodes table with columns for the node ID, latitude, longitude, and other attributes.

Once the database schema is in place, we can use the PostgreSQL JDBC driver to connect to the database and insert the OSM data. For each OSM element in the XML file, such as nodes, ways, and relations, we can insert the corresponding data into the appropriate table using SQL INSERT statements.

Before inserting the data, we might want to perform some pre-processing, such as filtering out unwanted elements or transforming the data into a different format. This can be done using Java code that operates on the XML data before inserting it into the database.

Overall, parsing OSM XML to a database from scratch requires a combination of skills in programming and database management. However, it provides more flexibility and control over the data loading process than using third-party tools such as `osm2pgsql`. It also allows us to customize the data loading process to fit our specific needs and requirements.