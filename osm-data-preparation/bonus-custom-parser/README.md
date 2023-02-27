# Lesson 6. Custom OSM XML parser (Bonus)

We used `osm2pgsql` to fill the database from the extracted file. But what if we want more flexibility in this process?

OpenStreetMap (OSM) data can be parsed and loaded into a database from scratch using a combination of programming languages and tools. In this lesson, we will use Java and PostgreSQL to parse an OSM XML file and load it into a PostgreSQL database.

To parse the XML file, we can use a Java XML parser library such as javax.xml.stream, which is included in the Java standard library. This library provides an event-driven parsing model that allows us to iterate through the XML elements and extract the necessary data.

First, you must create XMLInputFactory. Then you must create XMLStreamReader with use of this factory.

The reading code block should look similar to this:
```
while (reader.hasNext()) {
    int eventType = reader.next();
    switch (eventType) {
        case XMLStreamReader.START_ELEMENT:
            String elementName = reader.getLocalName();
            if (elementName.equals("node"))
                return readNode(reader);
            break;
        case XMLStreamReader.END_ELEMENT:
            break;
    }
}
```

To map the OSM data to Java objects, we will create a set of entity classes that represent the various OSM elements, such as nodes, ways, and relations. Each entity class will contain the necessary fields and annotations to map the corresponding OSM data attributes to database columns.

Nodes have attributes 'id' (node's id), 'lat' (latitude), 'lon' (longitude) and child tags `<tag>` with attributes 'k' (key) and 'v' (value).

Ways have attribute 'id' (way's id) and child tags `<nd>` with attribute 'ref' (reference id) and `<tag>` with attributes 'k' (key) and 'v' (value).

Relations have attributes 'id' (relation's id) and child tags `<member>` with attributes 'type', 'ref' (reference id), 'role' and `<tag>` with attributes 'k' (key) and 'v' (value). 

Most common tags for each type can be found in OSM docs.

Once we have our entity classes defined, we can use Hibernate to create the necessary database schema based on the entity mappings. Hibernate will automatically generate SQL statements to create the required tables and columns based on the entity mappings.

With the database schema in place, we can use Hibernate to insert the OSM data into the database. For each OSM element in the XML file, we can create a corresponding Java object, set its attributes based on the XML data, and then save the object to the database using Hibernate's built-in persistence mechanisms.

Before inserting the data, we can also perform some pre-processing using Java code, such as filtering out unwanted elements or transforming the data into a different format. Hibernate provides various hooks and extensions that allow us to customize the data loading process to fit our specific needs and requirements.

Overall, parsing OSM XML to a database from scratch requires a combination of skills in programming and database management. However, it provides more flexibility and control over the data loading process than using third-party tools such as `osm2pgsql`. It also allows us to customize the data loading process to fit our specific needs and requirements.