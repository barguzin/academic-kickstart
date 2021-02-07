---
title: "Installing Geo Stack with Manjaro"
date: 2021-02-07T00:39:25-08:00
draft: true
---

Installing geo-spatial stack on any Linux distribution may seem straight-forward and problem-free, but the closer one lives to the FOSS bleeding edge, the higher the chances for running into issues along the way. This was a case for me when I tried installing the geospatial stack via pip. First of, Manjaro ships with Python 3.8.5, so depending on the support of packages the migration and support of the current Python release could be slow. Hence, I warn all novice geo-spatial users out there to approach the installation process with utmost attention to the announced package compatibility and support. This guide is only one way to install the geo-spatial stack, and it is not 100% complete, so take it with a grain of salt and by all means experiment and invent some better ways. 

### The basics 

There are many different packages that form the basis of Python geo-spatial stack, including: 

1. Geopandas 
2. Pysal 
3. Shapely 
4. Fiona 
5. Rasterio 
6. GDAL

For a more complete list check out [this]((https://github.com/giswqs/python-geospatial)) Github page. Suffice it to say that these are the packages of various function, maturity and learning curve, so you will have to make some choices depending on your goals and expertise. For those of you familiar with **pandas** I suggest starting with **geopandas** as it provides familiar command lexicon and data structures, while allowing for spatial analysis and plotting. While the in-depth introduction to the package is out of scope of this blog post, I would like to share an easy sequence of command that I ordinarily use in my spatial analysis pipelines: 

```python
import geopandas as gpd

# easily read shapefiles 
gdf = gpd.read_file('MyShapefile.shp') 
gdf.head()

# plot choropleth
gdf.plot(column='myColumn') 

# set projection with a one-liner
gdf.set_crs(epsg=4326)

# reproject to Pseudo Mercator 
gdf.to_crs(epsg=3857)

# save 
gdf.to_file('MyShapefile_PMWGS.shp')
```

