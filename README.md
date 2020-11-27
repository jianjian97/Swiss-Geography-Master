# King of Geography
Student project as part of the course "Programming with Advanced Computer Languages" by Mario Silic in the Autumn Semester 2020. Fun game to learn more about Switzerland in a few minutes and to improve your knowledge of Swiss Geography!

## Table of contents
* [General info](#general-info)
* [Technologies](#technologies)
* [Setup](#setup)
* [Program Structure](#program-structure)
* [Short Libraries Description](#short-libraries-description)

## General info
This project's idea is to increase the general awareness of the Swiss geography and to show our students some (fun) facts about Switzerland. The program will be showing where the cantons' capitals are located on the map and will also give the students an intuition about how populated each cantons are. There will also be a few facts about mountains, lakes and other famous sightseeing spots. The program is split up into multiple sections or so-called chapters. There will be a learning section and a gaming section. For more information, please refer to the [Program Structure](#program-structure).

For simplicity, we refer to the user as "user" and "student" in the whole code and use the masculine pronoun "he". Under the pronoun "he" "him" "his" we wants to include any gender.
	
## Technologies
* Python version: 3.6
* Libraries used: pandas, folium, random, tkinter, json, numpy, locale, json (for description refer to [Short Libraries Description](#short-libraries-decription))
	
## Setup
To run this project, we recommend using Jupyter Notebooks/Anaconda. Please also use PowerShell by Anaconda to install the following locally:

```
$ pip install folium
$ pip install pandas
$ pip install tkinter
```

## Program Structure

### CHAPTER 0: IMPORT DATA AND PACKAGES
This is a short introduction step to analyze the data and import all packages. This is an important step for the rest of the code to be executed correctly and without errors.

### CHAPTER 1: PRELIMINARY STEPS TO CREATE THE MAP
In our first part we want to build a map, we prepare all the necessary data in this chapter.

### CHAPTER 2: CREATE THE MAP WITH MARKERS
We create an interactive map, where the user can click on different locations and gain information.

### CHAPTER 3: CHECK WHAT YOU LEARNED
We make a small pre-quiz for the user and show him the answer on the map for him to learn.

### CHAPTER 4: LAST CHECK BEFORE THE GAME
The user is given a last chance to check for some cities on the map before the game starts!

### CHAPTER 5: LET'S START THE GAME!
The user is then ready to start playing!

## Short Libraries Description

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
