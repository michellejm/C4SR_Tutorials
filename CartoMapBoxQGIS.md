# When to use Carto versus Mapbox versus QGIS

The purpose of this tutorial is to give a general overview of tools and techniques we will be using throughout the course. While this tutorial is technologically very light, it presents a series of questions and discussion that you want to address before embarking on a new project.

**By the end of this tutorial you will be able to:**

1. Identify which mapping platform(s) you will use in your final project.
2. Articulate the purpose and goal of your final project.
3. Justify your decision to use a particular tool based on the goals and objectives of your project.

## Introduction

Near the beginning of any project comes the question "what platform/program/language am I going to use to make this great thing?" When embarking on a mapping project (where "mapping" is broadly defined to be anything with a spatial component), there are five major platforms to use, Carto (formerly CartoDB), Mapbox, QGIS, ArcGIS, and Google Maps. 

ArcGIS and Google Maps are not covered here. Without an institutional license, ArcGIS is prohibitively expensive (and it only runs on Windows). However, most of what I will say about QGIS applies to ArcGIS. Google Maps is not covered either because while Google Maps is a convenient tool to mark locations, users do not have control over the visual effects of the final project. 

To get started, we have to ask a few questions to identify the goals of the project. 

**1. Is the purpose of this project to represent data in a spatial way or analyze spatially-bound data?**

Representing data in a spatial way means there is some information about the world that you want to associate with a place. This is often thought of as "dropping pins" or otherwise representing objects, events, or features on a map. For example, if you wanted to make a [map of language neighborhoods](https://michellejm.github.io/C4SR_Tutorials/) in New York City, you would draw polygons over a maps of NYC to represent neighborhoods.

Analyzing spatially-bound data may not involve "mapping" at all. This could be analyzing datasets with respect to each other with or without ever plotting any points. For example, if you wanted to analyze the languages spoken near to the [subway stations](http://subwaylanguages.michelleajohnson.com/), you would find out where all the subway stations are located and draw circles or boundaries (buffers) around them and see how that intersects with census data. 

In one approach, the map is the end goal. In the other approach, the data is the end goal. While all of the tools we will look at (Carto, Mapbox, QGIS) can help you achieve both of these goals, they have different strengths.

* Carto and MapBox are both great tools for representing data in a spatial way. They work well for creating an image to insert into a website, pdf, or to stand alone as a web-based object. Both have built-in themes and basemaps that you can draw on to illustrate information on your map. 
* QGIS is a great tool for analyzing spatially-bound data. There are a lot more functions such as creating buffers, clipping sections, merging layers, dissolving boundaries, creating unions, intersections, cutouts, etc. You cannot, however, start with a pre-made basemap and drop pins on it. In QGIS you will always import a file or group of files with information about the part of the world you want to focus on.

**2. How much control do you want to have over the way the map looks?**

The visual cues you embed into your map convey information in addition to the data you choose to display. As before, all of these platforms allow you to customize your map, but with different degrees of control and time investment.

* Mapbox is the strongest in this respect because it allows you to use a custom basemap and style it very easily.
* QGIS also allows the user to customize every detail of a map, but it takes more work because every feature of the map must be articulated.
* Carto is the weakest in this respect as it requires use of one of their basemaps. Customization is limited to what they have made available. 

**3. How many hours can you spend learning a new tool before you need a product?**

* To fully customize your map in QGIS will take some serious time.
* Carto has a much lower learning curve and it is possible to get very good results quickly.
* The learning curve for Mapbox is somewhere between the two. 
* One option is to use features of each tool to do individual tasks and then export it to another platform.

**4. Is the map exploratory or explanatory?**

When doing any geospatial research, there are two types of maps. The first is exploratory, to find out about the data. The second is explanatory, to tell a story about the data. While exploratory maps can represent the final project, they can also just be for you, the researcher, to determine what the interesting story is and how you want to tell it. Often, you will make an exploratory map before making and explanatory. The exploratory version may or may not bear any resemblance to the final project, but it should tell you somethign about the data that you have. Given this, efficiency is often the most important factor when making exploratory maps. 

**5. What format do you want to share your map in?**

Both Carto and Mapbox are designed for making webmaps - maps that can be shared via their website or embedded into another website. However, they use different approaches to make this happen. Mapbox uses vector tiles which are probably the most common modern approach. Carto uses a highly optimized database (PostGIS) system to call on each image. For most purposes, the results are similar. However, because of the technical details of how each system is build, Mapbox is more flexible and scalable. 

QGIS on the other hand is better for making print maps that can then be customized in another platform such as the Adobe Suite.

**For this course**
In this class, we will use all three of these tools for different purposes, illustrating the range of options you have available to you. However, in the final projects, you are free to use whichever tool is most appropriate for the goals of your project, and whichever tool is best equipt to help you tell the story you want to tell. 



