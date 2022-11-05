# python-api-challenge
Module 6 Assignment - Python API

## WeatherPy

### Code Theory

1. Had to do a pip install citipy
2. Pulled the API key from an external file. Will end up using .gitignore to remove the actual key strings
3. Ran tests to check if and what data was saved in the variables (Example: print(f"{cities}") )
4. Had a challenge in finding the right order in which to place the print statements. One outside the for loop to declare the beginning of the search, one right after the API call, one during the exception to show the city couldn't be found, then one outside the "try" statement to declare the data retrieval was completed.  
5. Created a dictionary to hold/define the columns from the json output
6. Created a dataframe to insert the data retrieved.
7. Saved the dataframe into a CSV.
8. Showed the data's general stats: count, mean, std, min, max, etc.
9. Removed the cities where the humidity was greater than or equal to 100%
10. I ran an extra check here to see the row count for the original DF and the new one without the full humidity. I was able to confirm I had rows with 100 or greater humidity.
11. I made a list of the index numbers and threw that into a variable total_humid. 
12. I dropped the rows that had the total_humid indexes and created a new DF.
13. Then I plot the data as described.  See my analysis below.
14. I had to use the epoch converter to check the dates. They're in unix epoch time and I wanted to ensure I had the correct date listed on each of the plots.
<hr>

## Latitude Plots

### Temperature (F) vs. Latitude <br/>
![Image](/Output/fig1.png)<br/>
**Analysis - Latitude vs. Max Temperature Plot**<br/>
* The cities located between Latitudes -20 and 20 have the highest Max Temps.
* The cities located between Latitudes 60 and 80 have the lowest Max Temps.
* It seems like the Max Temp generally gets lower as you move North on the globe.
<br/><br/>

### Humidity (%) vs. Latitude<br/>
![Image](/Output/fig2.png)<br/>
**Analysis - Latitude vs. Humidity Plot**<br/>
* Generally it seems most of our cities in the dataset have a Humidity of over 60%.
* Second group of popular Humidities (40-60%) seems to take place between Latitudes 20 and 60.
* The lowest Humidity (1%) belongs to Oslo, Norway.
<br/><br/>

### Cloudiness (%) vs. Latitude<br/>
![Image](/Output/fig3.png)<br/>
**Analysis - Latitude vs. Cloudiness Plot**
* The majority of the cities of this dataset seem to either have 0% or 100% Cloudiness.
* There is a concentration of cities with a 100% Cloudiness at the Equator (Latitude 0).
<br/><br/>

### Wind Speed (mph) vs. Latitude<br/>
![Image](/Output/fig4.png)<br/>
**Analysis - Latitude vs. Wind Speed Plot**
* Majority of the cities in this dataset have Wind Speeds below 15 MPH.
* Highest Wind Speeds appear around Latitudes: -45, 60 and 70.
* Notice another cluster of cities with similar wind speeds around the Equator (Latitud 0).
<br/><br/>

<hr>

## Linear Regression
Below the analysis was done after both hemispheres were plotted

### Temperature (F) vs. Latitude<br/>
![Image](/Output/north_tempvLat.png) ![Image](/Output/south_tempvLat.png)<br/>
**Analysis - Latitude vs. Max Temp Linear Regression for Northern & Southern Hemispheres**
* The Max Temps rise the closer you get to the Equator (Latitude 0) for both Northern and Southern Hemispheres.
* The slopes move in opposite directions when you compare the Northern and Southern Hemispheres and their relative Latitudes
* The Southern Hemisphere has more of a scattered data set for Max Temps than the Northern Hemisphere.
<br/><br/>

### Humidity (%) vs. Latitude<br/>
![Image](/Output/north_tempvHumid.png) ![Image](/Output/south_tempvHumid.png)<br/>
**Analysis - Latitude vs. Humidity Linear Regression for Northern & Southern Hemispheres**
* The Linear Regression was very similar for the Northern and Southern Hemispheres.
* There seems to be a lower number of cities in the dataset for the Southern Hemisphere.
<br/><br/>

### Cloudiness (%) vs. Latitude<br/>
![Image](/Output/north_tempvCloud.png) ![Image](/Output/south_tempvCloud.png)<br/>
**Analysis - Latitude vs. Cloudiness Linear Regression for Northern & Southern Hemispheres**
* There are extreme outliers for the Cloudiness at 0% and 100% for both Northern and Southern Hemispheres.
* The Southern Hemisphere shows more of a trend towards more clouds closer to the Equator (Latitude 0).
* The Northern Hemisphere doesn't seem to have any correlation.
<br/><br/>

### Wind Speed (mph) vs. Latitude<br/>
![Image](/Output/north_tempvWindSpd.png) ![Image](/Output/south_tempvWindSpd.png)<br/>
**Analysis - Latitude vs. Wind Speed Linear Regression for Northern & Southern Hemispheres**
* The Northern Hemisphere's city's Wind Speed don't often to go above 15 MPH.
* The Sothern Hemisphere's Wind Speed seems to lessen as you get closer to the Equator (Latitude 0).
* The correlation is stronger in the Northern Hemisphere.

<hr>
<hr>

## Vacation Py

### Code Theory
1. Once I had to move onto Part 2 of the assignment, I realized that some files were affected by having separate folders. So I decided to put both notebooks in the same folder to hand the api_keys.py file. It plays nicer that way.
2. Found I had to do a pip install of gmaps. Later on I also had to enable to extension.
3. When I plotted the first map, it was really small.  I ended up going back to the activities we covered during class to get the figure_layout specs.  I landed on 800px by 600px as a decent size, then just zoomed in.
4. Found there were a few places I had to keep changing the "lng" call to "long" because I changed it in Part 1 lol
5. This seemed easier because the first part had all the setup.
<hr>

### Google Maps

**Create a heat map that displays the humidity for every city from Part 1.**

Here is the saved image: <br/>
![Image](/Output/google-heatmap.png) <br/>

and the screenshot:<br/>
![Image](/Output/google-heatmap-screenshot.png)<br/><br/>

**Narrow down the DataFrame to find your ideal weather condition. Use Google Places API to find the first hotel for each city located within 5,000 meters of your coordinates. Plot the hotels on top of the humidity heatmap, with each pin containing the Hotel Name, City, and Country.**

Here is the saved image: <br/>
![Image](/Output/google-heatmap_markers.png) <br/>

and the screenshot:<br/>
![Image](/Output/google-heatmap_markers-screenshot.png)<br/><br/>
