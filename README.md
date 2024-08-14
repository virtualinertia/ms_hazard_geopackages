# Mississippi Hazard Layers Geopackages

This repository contains geospatial data in geopackage format. 
It includes layers considered helpful for teaching or learning about risk management.
The data are not vetted or updated and therefore are unsuitable and not intended for actual decision support.
Instead, they are collecions that are conveniently subsetted only for a single State and available in a consisent
Coordinate Reference System and projection (EPSG 4326). Geospatial data quickly scales into a Big Data problem.
Some of the layers included were only available in a U.S.-wide layer, in which case we subset them using the
Mississippi State Boundary multipolygon from the U.S. Census Bureau TIGER database. 
Users may decide for scalability to further subset by County, using the included TIGER County boundaries.

## Included Layers

The repository has a flood focus, including layers from:

* The National Levee Database (NLD)
* The National Bridge Inventory (NBI)
* The National Inventory of Dams (NID)

As well as an emergency response focus, including layers for:

* Police
* Fire Deparment
* Hospitals
* Schools
* Cell Towers (2018)

## Data Catalogs

Copies of the official data catalogs in PDF are included for the NLD, NID and NBI data sets. 
The actual data types in the geopackages are whatever the "sf" R package recognized them as,
since we used R in Posit Cloud to perform the following tasks:

* consume WFS web services
* read shapefiles and geopackages
* transform projecions
* subset for Mississippi
* remove invalid multipolygons
* serialize the results in geopackage format
  
Of particular note, all WFS properties for the NLD and NID WFS services were defined by those organizations as Strings. 
We did not recast numeric data, nor did we define enumerated values as factors, etc. 
Users will need to do a good deal of decoding with the data catalogs to understand, for example, what
"TYCUTO_ID" type "4" means.
("TYCUTO" is "The type of levee cutoff used to prevent seepage under the levee," and type "4" is "Slurry Wall".)
The NLD Data Dictionary in particular has a lot of uncataloged features and properties. 
We have provided an online version of [the NLD Data Catalog as a Shiny App](https://323kwp-alex-karman.shinyapps.io/nld_data_catalog/)) .



