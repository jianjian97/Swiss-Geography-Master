# King of Geography
Student project as part of the course "Programming with Advanced Computer Languages" by Mario Silic in the Autumn Semester 2020.

Fun game to learn more about Switzerland in a few minutes and to improve your knowledge of Swiss Geography!

## Table of contents
* [General info](#general-info)
* [Technologies](#technologies)
* [Setup](#setup)
* [Program Structure](#program-structure)
* [Libraries Description](#libraries-description)

## General info
This project's idea is to increase the general awareness of the Swiss geography and to show our students some (fun) facts about Switzerland. The program will be showing where the cantons' capitals are located on the map and will also give the students an intuition about how populated each cantons are. There will also be a few facts about mountains, lakes and other famous sightseeing spots. The program is split up into multiple sections or so-called chapters. There will be a learning section and a gaming section. For more information, please refer to the [Program Structure](#program-structure).

For simplicity, we refer to the user as "user" and "student" in the whole code and use the masculine pronoun "he". Under the pronoun "he" "him" "his" we want to include any gender.
	
## Technologies
* Python version: 3.6
* Libraries used: pandas, folium, random, tkinter, json, numpy, locale, json (for description refer to [Libraries Description](#libraries-description))
	
## Setup
To run this project, we recommend using Jupyter Notebooks/Anaconda. Please also use PowerShell by Anaconda to install the following locally:

```
$ pip install folium
$ pip install pandas
$ pip install tkinter
```

## Program Structure

### Chapter 0: Import data and packages
This is a short introduction step to analyze the data and import all packages. This is an important step for the rest of the code to be executed correctly and without errors. 
* Packages imported: pandas, folium, random, tkinter, json, numpy, locale, json
* Data imported: Population.xlsx, Coordinates.xlsx
All needed for the further illustration purpose of the map. The data includes all population numbers for the cantons and all coordinates for the pointers (mountains, capitals). We run some cross-checks that everything just appears once and there is no duplicates.

### Chapter 1: Preliminary steps to create the map
As first part of the game we want to create a map where the user will find red marker for the location of all Swiss cantons' capitals and blue marker for some Swiss Mountains/Glaciers. To show the map we use the folium package. For creating the marker on the map, we use the .marker function. We also want that when the user clicks on the marker, a message appears with the population of the canton. In this chapter, we prepare the text message in the marker.

### Chapter 2: Create the map with markers
At this stage, we now have our sentences and in our coordinates file, we have the coordinates of all cantons' capital in Switzerland. We can proceed and create the markers in folium.

Markers need the following elements:
* Coordinates: We find those by using our coordinates file, we know that the fourth column contains the latitutde data and the fith colum the longitude data. We use the brackets to find the relevant longitude and latitude for the relevant canton [line,column].
* Popup: We want then to specify the text that is written when the user click on the marker (popup). For this we created our list of sentences. Now to be easier to read the code,we specify the popup outside the folium.Marker() function (but it could be written inside directly). We define our popup using the folium.Popup() function. Please note that we use the max_width= and min_width= to definie the size of the box of our popup.
* Icon: We want our map to be pretty, so let's define our icon. (We found some information using the help(folium.Icon) function. Our map is informative so we want to have an icone with a "i" and therefore select the icon "info-sign" and also want to mark it red, for the user to see the marker well.

We also create an interactive map, where the user can click on different locations and gain information.

### CHAPTER 3: CHECK WHAT YOU LEARNED
We make a small pre-quiz for the user and show him the answer on the map for him to learn.

### CHAPTER 4: LAST CHECK BEFORE THE GAME
The user is given a last chance to check for some cities on the map before the game starts!

### CHAPTER 5: LET'S START THE GAME!
The user is then ready to start playing!

## Libraries Description

##### Pandas:
Pandas is an open-source, BSD licensed library that enables the provision of easy data structure and quicker data analysis for Python. For operations like data analysis and modelling, Pandas makes it possible to carry these out without needing to switch to more domain-specific language like R. Support for operations such as re-indexing, iteration, sorting, aggregations, concatenations and visualizations are among the feature highlights of Pandas. 

##### NumPy:
NumPy is one of the fundamental Python packages for scientific computing, as it provides support for large multidimensional arrays and matrices along with a collection of high-level mathematical functions to execute these functions swiftly. This interface can be utilized for expressing images, sound waves, and other binary raw streams as an array of real numbers in N-dimensional. NumPy can also be used as an efficient multi-dimensional container of generic data. 

##### Locale: 
The locale module is part of Python’s internationalization and localization support library. It provides a standard way to handle operations that may depend on the language or location of a user. For example, it handles formatting numbers as currency, comparing strings for sorting, and working with dates. 

##### Folium: 
The Folium library builds on the data wrangling strengths of the Python ecosystem and the mapping strengths of the leaflet.js library. Folium makes it easy to visualize data that’s been manipulated in Python on an interactive leaflet map. It enables both the binding of data to a map for choropleth visualizations as well as passing rich vector/raster/HTML visualizations as markers on the map. The fact that the Folium results are interactive makes this library very useful for dashboard building. 

##### Random:
The random module implements pseudo-random number generators for various distributions. Almost all module functions depend on the basic function random(), which generates a random float uniformly in the semi-open range [0.0, 1.0). 

##### Tkinter:
The tkinter package (“Tk interface”) is the standard Python interface to the Tk GUI toolkit (Graphical User Interface). When Python is combined with the Tkinter library, it provides a fast and easy way to create GUI applications. In these applications Tkinter provides various controls, such as buttons, labels and text boxes. 

##### Json:
JavaScript Object Notation (JSON) is a standardized format commonly used to transfer data as text that can be sent over a network. The json library can parse JSON from strings or files. The library parses JSON into a Python dictionary or list. It can also convert Python dictionaries or lists into JSON strings. 
