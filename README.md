# Visualizing the Energy Grid

This project was completed in an internship at Terranexum. See [Terranexum's website](https://www.terranexum.com/). 

## Introduction

In this project, I learned how to use several data visualization and analysis libraries in order to graph the greenhouse gas emissions occurring on the power grid. In order to do so, I had
to research data sources showing major emission locations, power line locations, and emission quantities - and the sources that I found for that data are listed below under Data. Through creating visualizations, I was able to create maps (both static and interactive) that show major emission sources and their proximity to the power grid and find statistics on the percentage of emissions that occur very close to power infrastructure. 

I made a presentation explaining the whole project: [Presentation](https://www.canva.com/design/DAGKZRCzDJY/rIGIveh886ghJYd3qBonLg/view?utm_content=DAGKZRCzDJY&utm_campaign=designshare&utm_medium=link&utm_source=editor)

To use the notebooks, a user must download the necessary data for each notebook (each notebook has its required data in a header, and the links to download the data are below). It also may be necessary to download the below libraries.

## Major Libraries and Datasets

### Libraries
- [Pandas](https://pandas.pydata.org/docs/)
- [Geopandas](https://geopandas.org/en/stable/docs/user_guide.html)
- [OSMnx](https://osmnx.readthedocs.io/en/stable/index.html)
- [Plotly](https://plotly.com/)
- [SRAI](https://github.com/kraina-ai/srai)

### Data
- [OpenStreetMap](https://wiki.openstreetmap.org/wiki/Map_features) (through OSMnx)
- [eGRID](https://www.epa.gov/egrid)
- [HIFLD](https://hifld-geoplatform.hub.arcgis.com/pages/hifld-open)
- [EPA FLight Data](https://ghgdata.epa.gov/ghgp/main.do#/facility/?q=Find%20a%20Facility%20or%20Location&st=&bs=&et=&fid=&sf=11001100&lowE=-20000&highE=23000000&g1=1&g2=1&g3=1&g4=1&g5=1&g6=0&g7=1&g8=1&g9=1&g10=1&g11=1&g12=1&s1=1&s2=1&s3=1&s4=1&s5=1&s6=1&s7=1&s8=1&s9=1&s10=1&s201=1&s202=1&s203=1&s204=1&s301=1&s302=1&s303=1&s304=1&s305=1&s306=1&s307=1&s401=1&s402=1&s403=1&s404=1&s405=1&s601=1&s602=1&s701=1&s702=1&s703=1&s704=1&s705=1&s706=1&s707=1&s708=1&s709=1&s710=1&s711=1&s801=1&s802=1&s803=1&s804=1&s805=1&s806=1&s807=1&s808=1&s809=1&s810=1&s901=1&s902=1&s903=1&s904=1&s905=1&s906=1&s907=1&s908=1&s909=1&s910=1&s911=1&si=&ss=&so=0&ds=E&yr=2022&tr=current&cyr=2022&ol=0&sl=0&rs=ALL)
- [Canadian Open Source Data](https://search.open.canada.ca/data/?page=1&sort=metadata_modified+desc)
- [USGS State Border Data](https://www.sciencebase.gov/catalog/item/52c78623e4b060b9ebca5be5)

## *Data visualizations using Geopandas* 

A major section of this project consisted of learning how to obtain, handle, and graph data, and one of the major libraries to allow me to do so was geopandas. Geopandas allows a user to create efficient maps using shapefile and geojson data through creating geodataframes. 
- In the below graph, I learned how to obtain data from OpenStreetMap and graph that data with different colors according to what type of data was being graphed. (See notebook.ipynb for more information)
![Map of OpenStreetMap power data in Colorado](https://github.com/terranexum/cloud-ai/blob/main/images/OSMnx_PowerData.png)

- In the next graph, I learned how to overlay multiple data sources and use an extra data source to filter data. (See overLayingData.ipynb for more information)
![Overlayed map of OpenStreetMap and EPA Flight data](https://github.com/terranexum/cloud-ai/blob/main/images/overlayingDataFinal3.png)
- Using the above graph, I used pandas to create a dataframe with only the emissions sources inside 2.3 miles of the powergrid to extract data showing what percentage of emissions came from within 2.3 miles of the power grid.
![Extracted data from OpenStreetMap and EPA Flight data showing percentage of emissions inside the energy grid](https://github.com/terranexum/cloud-ai/blob/main/images/gridEmissionsFinal.png)

- I overlayed EPA Flight data about national major CO2 emission sources onto HIFLD data showing all US transmision lines to find only the EPA Flight emission sources that fell within 2.3 miles of the power grid.  * This map is interactive, so when the program is loaded the user can zoom into different sections of the map *
![Overlayed map of national HIFLD and EPA Flight data](https://github.com/terranexum/cloud-ai/blob/main/images/Interactive_National_Map.png)
- Using that overlay, I found the percetage of EPA Flight reported emissions that fell within 2.3 miles of the power grid and the percentage of EPA Flight emission sources that fell within 2.3 miles of the power grid. 
![Results from EPA Flight/HIFLD overlay](https://github.com/terranexum/cloud-ai/blob/main/images/Results_National.png)

- I also found the percentage of greenhouse gas emissions that were inside 2.3 miles of a transmission line by state, and graphed each state's percentage in a choropleth map. 
![State-level percentage of GHG emissions within 2.3 miles of a transmission line](https://github.com/terranexum/cloud-ai/blob/main/images/Percentages_State.png)

## *Data visualizations using Plotly*

I also experimented with using Plotly for visualizations. Plotly is another library that allows for more interactive data visualization. In the below graph, the data in the graph being shown could be switched between three different data sets depending on a user selection. 
![Bar graph of CO2 emissisons with selection dial](https://github.com/terranexum/cloud-ai/blob/main/images/Plotly_BarGraph.png)

## *AI data analysis using SRAI*

- I began experimenting with using SRAI, an AI Python library that supports geospatial data analysis. I used SRAI to regionalize and embed spatial data about transmission lines in Denver, CO create a map showing the spatial distrobution of transmission lines in Denver. 
![Map of Denver transmission lines](https://github.com/terranexum/cloud-ai/blob/main/images/SRAI_Map.png)
-I repeated the same process to show the density of transmission lines across Colorado as well. 
![Map of Colorado transmission lines](https://github.com/terranexum/cloud-ai/blob/main/images/SRAI_Colorado_Map.png)