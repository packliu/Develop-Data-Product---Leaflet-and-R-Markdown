---
title: "Developing Data Products, Week2 Assignment"
author: "DomoM"
date: "October 2020"
output: 
  html_document:
    keep_md: true
---


## R Markdown and Leaflet
create a map with Leaflet and generate a web page using R Markdown. The circles size reresent the area (sq mi).


```r
library(leaflet)
```

```
## Warning: package 'leaflet' was built under R version 4.0.3
```

```r
my_trip <- data.frame(name = c("Seattle", "Mt. Rainier", "Vancouver"), 
                      pop = c(142.07, 369.3, 114.97), 
                      lat = c(47.608013, 46.879967, 49.246292),
                      lng = c(-122.335167, -121.726906, -123.116226))
my_trip %>%
  leaflet() %>%
  addTiles() %>%
  addCircles(weight = 1, radius = sqrt(my_trip$pop)*5000)
```

```
## Assuming "lng" and "lat" are longitude and latitude, respectively
```

<!--html_preserve--><div id="htmlwidget-34f436df4d64fdf5f9fb" style="width:672px;height:480px;" class="leaflet html-widget"></div>
<script type="application/json" data-for="htmlwidget-34f436df4d64fdf5f9fb">{"x":{"options":{"crs":{"crsClass":"L.CRS.EPSG3857","code":null,"proj4def":null,"projectedBounds":null,"options":{}}},"calls":[{"method":"addTiles","args":["//{s}.tile.openstreetmap.org/{z}/{x}/{y}.png",null,null,{"minZoom":0,"maxZoom":18,"tileSize":256,"subdomains":"abc","errorTileUrl":"","tms":false,"noWrap":false,"zoomOffset":0,"zoomReverse":false,"opacity":1,"zIndex":1,"detectRetina":false,"attribution":"&copy; <a href=\"http://openstreetmap.org\">OpenStreetMap<\/a> contributors, <a href=\"http://creativecommons.org/licenses/by-sa/2.0/\">CC-BY-SA<\/a>"}]},{"method":"addCircles","args":[[47.608013,46.879967,49.246292],[-122.335167,-121.726906,-123.116226],[59596.5603034269,96085.8990695305,53612.0322315802],null,null,{"interactive":true,"className":"","stroke":true,"color":"#03F","weight":1,"opacity":0.5,"fill":true,"fillColor":"#03F","fillOpacity":0.2},null,null,null,{"interactive":false,"permanent":false,"direction":"auto","opacity":1,"offset":[0,0],"textsize":"10px","textOnly":false,"className":"","sticky":true},null,null]}],"limits":{"lat":[46.879967,49.246292],"lng":[-123.116226,-121.726906]}},"evals":[],"jsHooks":[]}</script><!--/html_preserve-->

```r
my_trip
```

```
##          name    pop      lat       lng
## 1     Seattle 142.07 47.60801 -122.3352
## 2 Mt. Rainier 369.30 46.87997 -121.7269
## 3   Vancouver 114.97 49.24629 -123.1162
```
