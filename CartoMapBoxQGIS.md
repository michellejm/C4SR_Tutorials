# When to use Carto versus Mapbox versus QGIS

This is a very practical tutorial to help you get started making choices about which mapping platform you will use. This is intended for students, researchers, and academics who have data with any kind of a spatial dimension.

Near the beginning of any project comes the question "what platform/program/language am I going to use to make this great thing?" When embarking on a mapping project (where "mapping" is broadly defined to be anything with a spatial component), there are five major platforms to use, Carto (formerly CartoDB), Mapbox, QGIS, ArcGIS, and Google Maps. 

ArcGIS and Google Maps are not covered in this tutorial. Unless you have an institutional license, ArcGIS is prohibitively expensive and it only runs on Windows Computers. However, most of what I will say about QGIS applies to ArcGIS. Google Maps is not covered either because while Google Maps is a very easy tool to mark the location of something, users do not have control over what the final product looks like and how information is displayed. For academic and journalistic projects, controlling how the message is delivered is of utmost importance.

To get started, we have to ask a few questions to identify the goals of the project. 

**1. Is the purpose of this project to represent data in a spatial way or analyze spatially-bound data?**

Representing data in a spatial way means there is some information about the world that you want to associate with a place. This is often thought of as "dropping pins" or otherwise representing objects, events, or features on a map. For example, if you wanted to make a [map of language neighborhoods](https://michellejm.github.io/C4SR_Tutorials/) in New York City, you would draw polygons over a maps of NYC to represent neighborhoods.

Analyzing spatially-bound data may not involve "mapping" at all. This could be analyzing datasets with respect to each other with or without ever plotting any points. For example, if you wanted to analyze the languages spoken near to the [subway stations](http://subwaylanguages.michelleajohnson.com/), you would find out where all the subway stations are located and draw circles or boundaries (buffers) around them and see how that intersects with census data. 

In one approach, the map is the end goal. In the other approach, the data is the end goal. While all of the tools we will look (Carto, Mapbox, QGIS) can help you achieve both of these goals, they have different strengths.

* Carto and MapBox are both great tools for representing data in a spatial way. They work well for creating an image to insert into a website, pdf, or to stand alone as a web-based object. Both have built-in themes and basemaps that you can draw on to illustrate information on your map. 
* QGIS is a great tool for analyzing spatially-bound data. There are a lot more functions such as creating buffers, clipping sections, merging layers, dissolving boundaries, creating unions, intersections, cutouts, etc. You cannot, however, start with a pre-made basemap and drop pins on it. In QGIS you will always import a file or group of files with information representing the part of the world you want to focus on.

**2. How much control do you want to have over the way the map looks?**

The visual cues you embed into your map convey information in addition to the data you choose to display. As before, all of these platforms allow you to customize your map, but with different degrees of control and time investment.

* Mapbox is the strongest in this respect because it allows you to use a custom basemap, vector tiles (essentially map pieces that can be customized), and every feature of the visual experience. 
* QGIS also allows the user to customize the map, but it takes more work because every feature of the map must be customized.
* Carto on the other hand requires use of one of their basemaps. Customization is limited to what they have made available. 

**3. How many hours can you spend learning a new tool before you need a product?**

* The learning curve for Carto is much lower than the learning curve for QGIS. Mapbox is somewhere in between. 
* This is a legitimate question, and the reason why many professionals (journalists, academics, etc.) use Carto or MapBox rather than QGIS. 
