# Swiss Geography Master - Learn Switzerland's Geography with Python
Hi there! You just found the student project "Swiss Geography Master", which is part of the course "Programming with Advanced Computer Languages" by Mario Silic (Autumn Semester 2020 at the University of St. Gallen). The result of this project is a fun game built with Python to learn more about Switzerland in a few minutes and to improve your knowledge of Switzerland's geography! If this intrigues you, please read on and get more information!

## Table of contents
* [General Information](#general-information)
* [Technologies](#technologies)
* [Setup](#setup)
* [Program Structure](#program-structure)
* [Libraries Description](#libraries-description)
* [Authors](#authors)

## General Information
This project's goal is to increase the general awareness of the Swiss geography and to show our students some (fun) facts about Switzerland. The program shows where the cantons' capitals and other Swiss landmarks are located on the map and also gives the students an intuition about how populated each canton is. There are also a few facts about mountains, lakes and other famous sightseeing spots. The program is divided into multiple sections or so-called chapters. There is a learning section and a gaming section. For more information, please refer to the [Program Structure](#program-structure).

For simplicity, we refer to the user as "user" or "student" in the whole code and use the masculine pronoun "he". Under the pronouns "he", "him", and "his" we want to include any gender.
	
## Technologies
* Python version: 3.8.3
* Jupyter Notebook: To install Juypter Notebook, please refer to https://jupyter.org/install
* Libraries used: `pandas`, `numpy`, `locale`, `folium`, `random`, `tkinter`, `json`, `math` (for description refer to [Libraries Description](#libraries-description))
	
## Setup
To run this project, we recommend using Jupyter Notebook/Anaconda. Please also use PowerShell by Anaconda to install the following libraries locally:

```
$ pip install folium
$ pip install pandas
$ pip install tkinter
```

## Program Structure

### Chapter 0: Import data and packages
This is a short introduction step to analyze the data and import all packages. This is an important step for the rest of the code to be executed correctly and without errors. 
* Packages imported: `pandas`, `numpy`, `locale`, `folium`, `random`, `tkinter`, `json`, `math`
* Data imported: `Population.xlsx`, `Coordinates.xlsx`. All needed for the further illustration purpose of the map. The data includes all population numbers for the cantons and all coordinates for the pointers (mountains, capitals). We run some cross-checks that everything just appears once and there is no duplicates.

### Chapter 1: Preliminary steps to create the map
As first part of the game, we create a map where the user finds red markers for the locations of all Swiss cantons' capitals and blue markers for some Swiss landmarks. To show the map we use the `folium` package. To create the markers on the map, we use the `.Marker` function. When the user clicks on the marker, a message appears with the population of the canton. In this chapter, we prepare the text message of the markers.

### Chapter 2: Create the map with markers
At this stage, we now have our sentences and in our coordinates file, we have the coordinates of all cantons' capitals in Switzerland. We can proceed and create the markers in `folium`.

The markers need the following elements:
* Coordinates: We find those by using our coordinates file, we know that the fourth column contains the latitutde data and the fifth column the longitude data. We use the brackets to find the relevant longitude and latitude for the relevant canton [line,column].
* Popup: We want then to specify the text that is written when the user click on the marker (popup). For this we created our list of sentences. Now to be easier to read the code, we specify the popup outside the `folium.Marker()` function (but it could be written inside directly). We define our popup using the `folium.Popup()` function. Please note that we use the `max_width=` and `min_width=` to definie the size of the box of our popup.
* Icon: We want our map to be pretty, so let's define our icon. (We found some information using the `help(folium.Icon)` function. Our map is informative so we want to have an icon with an "i" and therefore select the icon "info-sign" and also want to mark it red, for the user to see the marker well.

We create the markers in red for the cantons' capital and blue for the landmarks. For the landmarks, we adjust the function dynamically to account for further new inputs. This means that when we add a new landmark to the list, it will automatically update the map. We do this by counting the numbers of "non-canton-objects" and appending them to the loop function.

At the end, we create an interactive map, where the user can click on different locations and gain information.

### Chapter 3: Check what you learned
We make a small pre-quiz for the user and show him the answer on the map for him to learn.

First, we create a list of two random cities. For this we use the random package and the random.sample command. We can calculate how many items we have in total in our coordinates data frame subtracted the number of mountains/glaciers. Then we use the sample command, and ask it to select 2 elements out of the range of the number of cantons. The two random cantons are stored in the random list with numbers between 0 and 25.

Then, we create the game where we explain the rules, keep the score and account for the input of the user. At the end, we check for the answer of the user with an if function and we do not take any input other than the given "E,W,S,N" answers.

The score of the student is printed using the sum function on our score list. Additionally, the two selected cities are shown on a map for a visual check.

### Chapter 4: Last check before the game
The user is given a last chance to check for some capitals on the map before the game starts.
We explain the rules to the user and show him our coordinates dataframe. But we don't want to confuse him. We therefore only select the rows with the cities in the data frame with the `.iloc` command.

Furthermore, we ask the student to input a number of capitals that he would like to check and also ask him to input the corresponding abbreviation of the cantons. For the sake of this, we create a dictionary which allocates the right number with the canton's name. We use our dictionary to find out which abbreviation is in which row. Like that, the user enters the abbreviation of the canton but we save them as a number.

At the end, we create a new map that only shows the user's inputs.

### Chapter 5: Let's start the game!
The user is then ready to start playing the game. Note that this is a quiz that contains 30 questions. Each round randomly extracts 5 questions for the user to answer and the maximum score of the game is 5.

The quiz code has been taken from a youtube tutorial (https://www.youtube.com/watch?v=ES8GDaBbgEI&t=1s). Our group amended some of the graphics and also the additional part where the final score will be showing up at the end. We also added a quit button at the end and a "try again" button to restart the quiz.

## Libraries Description

##### Pandas:
`pandas` is an open-source, BSD licensed library that enables the provision of easy data structure and quicker data analysis for Python. For operations like data analysis and modelling, `pandas` makes it possible to carry these out without needing to switch to more domain-specific language like R. Support for operations such as re-indexing, iteration, sorting, aggregations, concatenations and visualizations are among the feature highlights of `pandas`. 

##### NumPy:
`numpy` is one of the fundamental Python packages for scientific computing, as it provides support for large multidimensional arrays and matrices along with a collection of high-level mathematical functions to execute these functions swiftly. This interface can be utilized for expressing images, sound waves, and other binary raw streams as an array of real numbers in N-dimensional. `numpy` can also be used as an efficient multi-dimensional container of generic data. 

##### Locale: 
The `locale` module is part of Python’s internationalization and localization support library. It provides a standard way to handle operations that may depend on the language or location of a user. For example, it handles formatting numbers as currency, comparing strings for sorting, and working with dates. 

##### Folium: 
The `folium` library builds on the data wrangling strengths of the Python ecosystem and the mapping strengths of the `leaflet.js` library. `folium` makes it easy to visualize data that’s been manipulated in Python on an interactive leaflet map. It enables both the binding of data to a map for `choropleth` visualizations as well as passing rich vector/raster/HTML visualizations as markers on the map. The fact that the `folium` results are interactive makes this library very useful for dashboard building. 

##### Random:
The `random` module implements pseudo-random number generators for various distributions. Almost all module functions depend on the basic function `random()`, which generates a random float uniformly in the semi-open range [0.0, 1.0). 

##### Tkinter:
The `tkinter` package (“Tk interface”) is the standard Python interface to the Tk GUI toolkit (Graphical User Interface). When Python is combined with the `tkinter` library, it provides a fast and easy way to create GUI applications. In these applications `tkinter` provides various controls, such as buttons, labels and text boxes. 

##### Json:
JavaScript Object Notation (JSON) is a standardized format commonly used to transfer data as text that can be sent over a network. The `json` library can parse JSON from strings or files. The library parses JSON into a Python dictionary or list. It can also convert Python dictionaries or lists into JSON strings.

##### Math:
The `math` module is a standard module in Python and is always available. The library provides access to the mathematical functions defined by the C standard. All methods of this functions are used for integer or real type objects, not for complex numbers.

## Authors
Zachary Matteucci

Filippo Coduri

Nina Tuchschmid

