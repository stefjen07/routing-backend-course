# Lesson 3. OSM data conversion and filtering

[Osmium](https://osmcode.org/osmium-tool/) is [a command-line interface](https://en.wikipedia.org/wiki/Command-line_interface) (CLI) tool for working with OpenStreetMap (OSM) data that provides powerful tools for reading, processing, and writing OSM data in different file formats. Osmium is written in C++ and provides a fast and efficient engine for handling large OSM datasets. However, it also provides a CLI interface that allows users to access the Osmium engine without needing to write any C++ code.

Using Osmium as a CLI tool, you can perform a wide range of OSM data processing tasks, including converting between different file formats, filtering data based on specific criteria, and extracting data from OSM databases. Osmium also provides several built-in modules that can perform complex tasks, such as calculating the shortest path between two nodes or generating a heatmap of OSM data.

To use Osmium as a CLI tool, you need to install it on your computer, which can be done using your operating system's package manager or by compiling from source code. Once installed, you can run Osmium commands in the terminal or command prompt, using the following syntax:

```
osmium <command> [options] <input file> [<output file>]
```

For example, to convert an OSM PBF file to an XML file, you can use the following command:

```
osmium cat input.osm.pbf -o output.xml
```

This command will read the input file input.osm.pbf, convert it to XML format, and write the output to the file output.xml. Similarly, to filter OSM data based on specific criteria, you can use the following command:

```
osmium tags-filter input.osm.pbf -o output.osm.pbf "amenity=restaurant"
```

This command will read the input file input.osm.pbf, filter the data based on the amenity=restaurant tag, and write the output to the file output.osm.pbf.

Overall, Osmium is a powerful CLI tool for processing OSM data that can handle large datasets efficiently and provide flexible and customizable workflows without needing to write any C++ code.

## Task

You need to convert the downloaded file (from the previous lesson) from PBF to XML. As the result, you must provide screenshots of your converted file properties.