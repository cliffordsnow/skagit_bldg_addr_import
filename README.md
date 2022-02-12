# Skagit County Building and Address Import

*Not ready for import*

#### Building and Address Import
This project will import data from Skagit County. Skagit County provides a wide array of data from their website, including road centerlines and buildings. While they don't include E911 address information they were willing to provide their data for use in OSM. 
The import process will use the US Tasking Manager. Washington Voting District data will be used to break the import into 124+ small tasks.

#### License
Skagit County offer open data with no strings attached. They do request that credit to Skagit County GIS as the data source which will be documented on the wiki.

#### Process
This process is built on using PostGIS and Python. It was originally developed using Fedora 24 and updated for Fedora 35. It should work on MacOS.
To use the process, clone the repository and modify the import.sh and skagit_osm.sh scripts to define your working directory and access to Postgresql. Before running the scripts, add the functions below to your PostGIS/Postgresql server. They are needed to convert the road names into ones that OSM like.
- run import.sh to build the Postgresql tables
- run skagit_osm.sh to build individual .osm files for import

#### Requirements
* PostGIS
* Python
* Postgresql functions from my [sql](https://github/cliffordsnow/sql) repository
```
expand_directions.sql
expand_roads.sql
format_roads.sql
fullname.sql
