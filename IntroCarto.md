#Carto Tutorial - Getting Started on Carto

##Part I - Account Set Up

You will need to set up a (free) account on Carto at www.carto.com. You only need an email and password, the questions are optional. If you have GitHub, I encourage you to sign up using your GitHub account so that any files you store (or update) on GitHub can be easily imported into your map.

Once you set up an account, you will be taken to the page to Add Datasets. We are going to be working with some Census Data about income and language in New York City. First we need to decide what kind of boundaries we are going to use. For this tutorial, we will use Census Tracts (click here for more on the different types). 

This dataset comes from the [American Community Survey](www.factfinder.census.gov). For more on finding datasets, visit ANOTHER GITPAGE. 

##Part II - Uploading Data

The data we are using for this tutorial is pre-cleaned. We will have another session on finding and cleaning data.

1. Import shapefile of census tracts for New York State
This file came from [the US Census](https://www.census.gov/geo/maps-data/data/cbf/cbf_tracts.html), though it is available in multiple locations, multiple ways
	a. Go to SHAREFOLDER
	b. Find "gz_2010_36.csv" 
	c. Return to Carto >> Add Dataset
	d. Upload the file here
	e. Carto will show you the map view. It should look like New York State divided into census tracts.
	f. Return to Data View (with the slider at the top)
	g. For clarity, I'm going to edit the metadata and rename my dataset "nyc_censustracts"

2. Add more data from a file

Now we are going to add language information to the census tracts. The data came from [National Historical GIS](https://www.nhgis.org/). It has been pre-cleaned for this tutorial. For more on data cleaning visit ANOTHER GITPAGE.
	a. Go to SHAREFOLDER
	b. Find "nhgis_language_percents_nyc.csv"
	c. Open this file to inspect it
	d. Notice the Column named 'GISJOIN' this is the column we are going to use to merge those two datasets. Look back at the census tract file. It also has a GISJOIN column. These numbers correspond to each census tract.
	e. Return to Carto and navigate back to the DataSets Page (*small arrow in left hand corner*)
	f. Upload the "nhgis_language_percents_nyc.csv" 
	g. It will not automatically show you a map view, so click on the slider to see the map view.
	h. It should ask you to Georeference the dataset. DO NOT GEOREFERENCE IT! There is no geographic information in this dataset - only statistical information.
	i. Return to DataSets
	
3. Combine Files
Now we are going to align the language information to the census tracts.
	a. Open the "NYS_censustracts" dataset
	b. Merge this dataset with another (Click Edit >> Merge with dataset) *This will create a new dataset*
	c. Select 'Column Join'
	d. Find the 'nhgis_language_percents_nyc' file
	e. Select 'cnty_tract' for both files, and click 'Next'
	f. All of the languages and county names should be selected. If they aren't, select them now.
	g. A new dataset will appear. I'm going to rename mine, "languages_by_censustract_nyc"
	h. Carto will probably suggest some "interesting maps" ignore these.
	
##Part III - Mapping data
In this section, we will look at the data in a map form. At this point, our questions are exploratory.

1. Make the data into a map
	a. In the upper right hand corner, click on 'Visualize'
	b. Carto will prompt you to make a map. Accept this.
	c. This changes your dataset from a spreadsheet with a spatial component into a map you can add layers to within the system.
	
2. Inspect the data
	a. Click on the number '1' in the box on the right side of the screen. This is the first layer. 
	b. If it isn't selected already, click on the little square with a paintbrush. This is the mapping 'wizard'. Eventually, you will create these maps manually, but for right now, let's just look at the built-in options.
	c. Select Choropleth. Choropleth maps are good for showing differences in density. Our language data is perfectly suited to this.
	d. Select any language. I'm going to choose Chinese.
	f. Does this align with what you might expect for the city? Why or why not?
	
3. Add a Tooltip
	a. Click on the 'infowindow' box directly below the 'wizard' box.
	b. There are two options here - 'click' and 'hover' - pick your preference.
	c. Select a language to show, I'm choosing Chinese since we're looking at the Chinese map.
	d. Go back to the map and either click or hover over one of the census tracts, two numbers should appear. 
		i. The decimal represents the percentage of speakers
		ii. The grey number represents the row where that datum appears in the table (only visible to you)

4. Formatting the Tooltip
*We want the tooltip to display as a percentage, not as a decimal. We can do this one of two ways. First, we could reformat the data in Excel, to natively be a percentage. Second, we can do it using SQL commands. I am going to chose the SQL commands because it gives me more control over the data.*
	a. Click on the icon that says 'SQL' (directly above the wizard)
	b. SQL is a very old computer language still used for databases. Carto is treating your dataset as a database, and Querying it for information. 
	c. We are going to change the query.
		i. Currently, it should say: **SELECT \* FROM languages_by_census_tracts_nyc** This means *select everything from the dataset, languages...* For this layer, Carto has access to all the information on your dataset. This layer is about Chinese, so we will restrict it to just Chinese.
		ii. Remove the original command and replace it with: **SELECT \*, to_char(chinese, '99V99%') AS chinese_percent FROM languages_by_census_tracts_nyc** *This says select everything from the dataset, languages..., and change the characters in the chinese column to a percent formal and call that transformation chinese_percent
		iii. Run this query by clicking 'Apply Query'
	d. Now return to the tooltip and select the new variable, chinese_percent (and deselect the old chinese).
		
5. Making layers
	a. In the last step, we make layer 1 for Chinese. Let's make another layer for Arabic.
	b. Click on 'Add Layer', directly above the Chinese layer
	c. We are going to do the same for Arabic that we did for Chinese.
	d. Select Choropleth Map view (Step 2)
	e. Apply the SQL filter for Arabic (Step 4)
	f. Add the tooltip (Step 3)
	g. Be sure to rename the layer
	h. Repeat for as many languages as you want

6. Customizing Views
	a. Toggle the visibility of layers by selecting the layer and moving the slider button on the top right hand side of the title bar.
	b. Add a layer selector to your map by changing the settings
		i. On the map, in the lower left corner is the 'Options' button.
		ii. Select 'Layer Selector'
		iii. Selection now appears in the upper right side of the map
	c. Add titles, legends, etc.
	
Congratulations! You have made your first map!! 
In future tutorials, we will drop pins, upload media, clean data for analysis, and more!
 
	
	

	