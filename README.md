# cloud-ai

This project was completed in an internship at Terranexum. See [Terranexum's website](https://www.terranexum.com/). 

## Major libraries and data used

### Libraries
- [Pandas](https://pandas.pydata.org/docs/)
- [Geopandas](https://geopandas.org/en/stable/docs/user_guide.html)
- [OSMnx](https://osmnx.readthedocs.io/en/stable/index.html)
- [Plotly](https://plotly.com/)

### Data
- [OpenStreetMap](https://wiki.openstreetmap.org/wiki/Map_features)(through OSMNX)
- [eGRID](https://www.epa.gov/egrid)
- [HIFLD](https://hifld-geoplatform.hub.arcgis.com/pages/hifld-open)
- [EPA FLight Data](https://ghgdata.epa.gov/ghgp/main.do#/facility/?q=Find%20a%20Facility%20or%20Location&st=&bs=&et=&fid=&sf=11001100&lowE=-20000&highE=23000000&g1=1&g2=1&g3=1&g4=1&g5=1&g6=0&g7=1&g8=1&g9=1&g10=1&g11=1&g12=1&s1=1&s2=1&s3=1&s4=1&s5=1&s6=1&s7=1&s8=1&s9=1&s10=1&s201=1&s202=1&s203=1&s204=1&s301=1&s302=1&s303=1&s304=1&s305=1&s306=1&s307=1&s401=1&s402=1&s403=1&s404=1&s405=1&s601=1&s602=1&s701=1&s702=1&s703=1&s704=1&s705=1&s706=1&s707=1&s708=1&s709=1&s710=1&s711=1&s801=1&s802=1&s803=1&s804=1&s805=1&s806=1&s807=1&s808=1&s809=1&s810=1&s901=1&s902=1&s903=1&s904=1&s905=1&s906=1&s907=1&s908=1&s909=1&s910=1&s911=1&si=&ss=&so=0&ds=E&yr=2022&tr=current&cyr=2022&ol=0&sl=0&rs=ALL)

## *Data visualizations using Geopandas* 

A major section of this project consisted with learning how to obtain, handle, and graph data, and one of the major libraries to allow me to do so was geopandas. Geopandas allows a user to create efficient maps using shapefile and geojson data through utilizing geodataframes. 
- In the below graph, I learned how to obtain data from OpenStreetMap and graph that data with different colors according to what type of data was being graphed. (See notebook.ipynb for more information)
![Map of OpenStreetMap power data in Colorado](https://github.com/terranexum/Cloud-AI/blob/dahl-dev/images/OSMnx_PowerData.png)

- In the next graph, I learned how to overlay multiple data sources and use an extra data source to filter data. (See overLayingData.ipynb for more information)
![Overlayed map of OpenStreetMap and EPA Flight data](https://github.com/terranexum/Cloud-AI/blob/dahl-dev/images/overlayingDataFinal3.png)
- Using the above graph, I used pandas to create a dataframe with only the emissions sources inside 2.3 miles of the powergrid to extract data showing what percentage of emissions came from within 2.3 miles of the power grid.
![Extracted data from OpenStreetMap and EPA Flight data showing percentage of emissions inside the energy grid](https://github.com/terranexum/Cloud-AI/blob/dahl-dev/images/gridEmissionsFinal.png)

- I overlayed EPA Flight data about national major CO2 emission sources onto HIFLD data showing all US transmision lines to find only the EPA Flight emission sources that fell within 2.3 miles of the power grid.  * This map is interactive, so when the program is loaded the user can zoom into different sections of the map *
![Overlayed map of national HIFLD and EPA Flight data](https://github.com/terranexum/Cloud-AI/blob/dahl-dev/images/Interactive_National_Map.png)
- Using that overlay, I found the percetage of EPA Flight reported emissions that fell within 2.3 miles of the power grid and the percentage of EPA Flight emission sources that fell within 2.3 miles of the power grid. 
![Results from EPA Flight/HIFLD overlay](https://github.com/terranexum/Cloud-AI/blob/dahl-dev/images/Results_National.png)

## *Data visualizations using Plotly*

I also experimented with using Plotly for visualizations. Plotly is another library that allows for more interactive data visualization. In the below graph, the data in the graph being shown could be switched between three different data sets depending on a user selection. 
![Bar graph of CO2 emissisons with selection dial](https://github.com/terranexum/Cloud-AI/blob/dahl-dev/images/Plotly_BarGraph.png)