# Python API - What's the Weather Like?

## Background

"What's the weather like as we approach the equator? How is the weather affect our life and the earth globally? 

Through this project, we explored the relationship with the latitudinal position between maximum temperature (F), humidity (%), cloudiness (%), and wind speen (mph) over 500+ cities worldwide. Hereby extend the technologies, gather the data with API keys from website: [OpenWeatherMap API](https://openweathermap.org/api) throuth those random data set vary from the equator, Northern or Southern Hemisphere, analysize via Python, NumPy, citiPy, SciPy through linear regression to determine whether correlation existed between city latitude and other elements from the result. Later on, the result could also help us to plan travel in good weather condition in different cities.

![latitude_worldmap](Images/latitude_worldmap.jpg)

### Technologies Used
Jupyter Notebook
Python - Pandas, JSON, Matplotlib, NumPy, SciPy, CitiPy, Gmaps, OS, Requests


### Data Sources
Cities CSV

### References
[OpenWeatherMap API](https://openweathermap.org/api), 

[citipy Python library](https://pypi.python.org/pypi/citipy),

[geographic coordinate system](http://desktop.arcgis.com/en/arcmap/10.3/guide-books/map-projections/about-geographic-coordinate-systems.htm),

[Google Maps Platform Billing](https://developers.google.com/maps/billing/gmp-billing#monitor-and-restrict-consumption),

[Manage your cost of use](https://developers.google.com/maps/documentation/javascript/usage-and-billing#set-caps)


### Preparing Ahead

1. Create a new repository called `python-api-challenge` and clone the new repository to your computer.

2. Inside the repository folder, add new files called `WeatherPy.ipynb` and `VacationPy.ipynb` for the main scripts to run for each analysis.

3. Push the above changes to GitHub.


### Adding A .gitignore File

To avoid `api_keys.py` file containing the API key to be exposed to the public on GitHub which possibly causing us to incur charges, we can add the files we don't want to track to the `.gitignore` file. This could keep our config file with API keys stays at local.

If we only wanted to add the `WeatherPy.ipynb` file to GitHub we could type `git add WeatherPy.ipynb`. However, every time we want to add a new file or update current files to the repository, we have to add each file individually, which is time-consuming and cumbersome. Instead, we can add the files we don't want to track to the `.gitignore` file.

When we type `git status` in the command line, we can see all the files we have created so far that are untracked.


Before we add our files to GitHub, let's add `api_keys.py` to the `.gitignore` file. Follow these steps:

1. Open your `python-api-challenge` GitHub folder in VS Code.

2. Open the `.gitignore` file, and on the first line type the following:

```python
# Adding config.py file.
api_keys.py
```

3. While the `.gitignore` file is open, add the `API_practice.ipynb` and `random_numbers.ipynb` files and save the file.

4. In the command line, type `git status` and press Enter. The output should say the `.gitignore` file has been modified and the `WeatherPy.ipynb` file is untracked.

5. Use `git add`, `git commit`, and `git push` to commit the modifications to `.gitignore` and the `WeatherPy.ipynb` file to GitHub.

On GitHub, the only new file you should see is the `WeatherPy.ipynb` file.


## Part I - WeatherPy

Creating a Python script to visualize the weather of 500+ cities across the world of varying distance from the equator. To accomplish this, you'll be utilizing a [simple Python library](https://pypi.python.org/pypi/citipy), the [OpenWeatherMap API](https://openweathermap.org/api), and a little common sense to create a representative model of weather across world cities.

1. create a series of scatter plots to showcase the following relationships:

* Temperature (F) vs. Latitude
* Humidity (%) vs. Latitude
* Cloudiness (%) vs. Latitude
* Wind Speed (mph) vs. Latitude

After each plot, add a sentence or two explaining what the code is analyzing.

2. run linear regression on each relationship. This time, separate the plots into Northern Hemisphere (greater than or equal to 0 degrees latitude) and Southern Hemisphere (less than 0 degrees latitude):

* Northern Hemisphere - Temperature (F) vs. Latitude
* Southern Hemisphere - Temperature (F) vs. Latitude
* Northern Hemisphere - Humidity (%) vs. Latitude
* Southern Hemisphere - Humidity (%) vs. Latitude
* Northern Hemisphere - Cloudiness (%) vs. Latitude
* Southern Hemisphere - Cloudiness (%) vs. Latitude
* Northern Hemisphere - Wind Speed (mph) vs. Latitude
* Southern Hemisphere - Wind Speed (mph) vs. Latitude

After each pair of plots, take the time to explain what the linear regression is modeling. For example, describe any relationships you notice and any other analysis you may have.

Your final notebook must:

* Randomly select **at least** 500 unique (non-repeat) cities based on latitude and longitude.
* Perform a weather check on each of the cities using a series of successive API calls.
* Include a print log of each city as it's being processed with the city number and city name.
* Save a CSV of all retrieved data and a PNG image for each scatter plot.

### Part II - VacationPy

Utilizing the weather data to plan future vacations. The Use jupyter-gmaps and the Google Places API for this part of the assignment.

* **Note:** Remember that any API usage beyond the $200 credit will be charged to your personal account. You can set quotas and limits to your daily requests to be sure you can't be charged. Check out [Google Maps Platform Billing](https://developers.google.com/maps/billing/gmp-billing#monitor-and-restrict-consumption) and [Manage your cost of use](https://developers.google.com/maps/documentation/javascript/usage-and-billing#set-caps) for more information.

* **Note:** if you having trouble displaying the maps, try running `jupyter nbextension enable --py gmaps` in your environment and retry.

To complete this part of the assignment,you will need to do the following:

* Create a heat map that displays the humidity for every city from Part I.

  ![heatmap](Images/heatmap.png)

* Narrow down the DataFrame to find your ideal weather condition. For example:

  * A max temperature lower than 80 degrees but higher than 70.

  * Wind speed less than 10 mph.

  * Zero cloudiness.

  * Drop any rows that don't contain all three conditions. You want to be sure the weather is ideal.

  * **Note:** Feel free to adjust to your specifications but be sure to limit the number of rows returned by your API requests to a reasonable number.

* Using Google Places API to find the first hotel for each city located within 5000 meters of your coordinates.

* Plot the hotels on top of the humidity heatmap with each pin containing the **Hotel Name**, **City**, and **Country**.

  ![hotel map](Images/hotel_map.png)

As final considerations:

* You must complete your analysis using a Jupyter notebook.
* You must use the Matplotlib or Pandas plotting libraries.
* For Part I, you must include a written description of three observable trends based on the data.
* For Part II, you must include a screenshot of the heatmap you create and include it in your submission.
* You must use proper labeling of your plots, including aspects like: Plot Titles (with date of analysis) and Axes Labels.
* For max intensity in the heat map, try setting it to the highest humidity found in the data set.

## Hints and Considerations

* The city data you generate is based on random coordinates as well as different query times. As such, your outputs will not be an exact match to the provided starter notebook.

* If you'd like a refresher on the geographic coordinate system, [this site](http://desktop.arcgis.com/en/arcmap/10.3/guide-books/map-projections/about-geographic-coordinate-systems.htm) has great information.

* Next, spend the requisite time necessary to study the OpenWeatherMap API. Based on your initial study, you should be able to answer basic questions about the API: Where do you request the API key? Which Weather API in particular will you need? What URL endpoints does it expect? What JSON structure does it respond with? Before you write a line of code, you should be aiming to have a crystal clear understanding of your intended outcome.

* A starter code for Citipy has been provided. However, if you're craving an extra challenge, push yourself to learn how it works: [citipy Python library](https://pypi.python.org/pypi/citipy). Before you try to incorporate the library into your analysis, start by creating simple test cases outside your main script to confirm that you are using it correctly. Too often, when introduced to a new library, students get bogged down by the most minor of errors -- spending hours investigating their entire code -- when, in fact, a simple and focused test would have shown their basic utilization of the library was wrong from the start. Don't let this be you!

* Use critical thinking skills to understand how and why we're recommending the tools we are. What is Citipy for? Why would you use it in conjunction with the OpenWeatherMap API? How would you do so?

* In building your script, pay attention to the cities you are using in your query pool. Are you getting coverage of the full gamut of latitudes and longitudes? !! Consider the full range of latitudes when choosing 500 cities from the world.

* Once computed the linear regression for one chart, the process will be similar for all others. As a bonus, try to create a function that will create these charts based on different parameters.

* Each coordinate will trigger a separate call to the Google API. If you're creating your own criteria to plan your vacation, try to reduce the results in your DataFrame to 10 or fewer cities.

* This challenging activity letting you safely say that you've gained a strong mastery of the core foundations of data analytics and it will only go better from here. 

- - -

?? 2021 Trilogy Education Services, LLC, a 2U, Inc. brand. Confidential and Proprietary. All Rights Reserved.
