# Athens AirBnB 2023 Dashboard

Research project in Tableau, regarding AirBnB data for Athens, Greece and resulting in a dashboard with useful insights for 2023.

The original dataset can be found in: http://insideairbnb.com/get-the-data/

Under the "Athens, Attica, Greece 27 December 2022" section, we download the first two detailed .csv.gz files ('listings.csv.gz' and 'calendar.csv.gz') and the last .geojson one ('neighbourhoods.geojson'). After transforming the .csv.gz files to plane .csv, we combine them in Excel, producing a single .xlsx file with two respective sheets, which can now be cleaned and later imported into Tableau. Here, it is of utmost importance to mention that when we load those two files in Excel, we must change the 'File Origin' to '65001: Unicode (UTF-8)' so that the Greek script is recognized by both Excel and Tableau.

The cleaning process is quite basic and mainly boils down to transforming the data type of two columns (column 'price' in both 'Listings' and 'Calendar' sheets) to 'Number' as well as deleting the dollar sign ($) from the beginning of each value in those columns.

Only then, we are ready to import our dataset into Tableau and apply two inner joins between our tables: 

1) between 'Listings' and 'Calendar', based on the 'id' column in 'Listings' and the 'listing_id' column in 'Calendar' and
2) between 'Listings' and 'neighbourhoods.geojson', based on the 'neighbourhood_cleansed' column in 'Listings' and the 'neighbourhood' column in 'neighbourhoods.geojson'.

After some exploratory analysis, we conclude with the final dashboard, including one pivot table and four different visualizations:

1) 'Amount of Listings per Amount of Bedrooms': in this pivot table we can clearly see how many listings/bookings were confirmed bedroomwise, that means how many reservations each type of house has, based on the number of bedrooms they provide,
2) 'Price by Bedrooms': in this visualization we can see the average price bedroomwise, again, 
3) 'Revenue for 2023': in this graph we can see the total revenue (sum of price) across 2023 on a weekly scale (Tableau also offers the interactive option of drilling the graph up or down to yearly, quarterly, monthly or daily scale),
4) 'Athens Map': in this map we can see the borders between distinct neighbourhoods of the center of Athens (here is where the .geojson file gets applied) and 
5) 'Price by Location': in this visualization we can see the average price of each different neighbourhood in the center of Athens.

In between the last two bottom visualizations, there is an interactive legend/filter where one or more neighbourhoods can be chosen, in order to selectively see both the average price and the location in the map.

# Insights

A lot could be said as for the insights someone could derive from this dashboard, nevertheless we can underline some obvious, though quite interesting information:

1) most reservations concern houses with maximum three bedrooms,
2) houses with six bedrooms achieve the highest average price, with significant difference from the rest,
3) the total revenue starts increasing in February, then drops in April to stay almost stable until late August when it starts gradually increasing again and 
4) the top three most expensive locations are: Agios Konstantinos - Plateia Vathis, Votanikos and Thiseio, which are generally not considered as expensive in the typical real estate market.

A screenshot of the outcome can be accessed through the .png file, however it is strongly recommended to experience the interactive options of Tableau via the .twbx file or directly via the published dashboard in my Tableau Public account: https://public.tableau.com/app/profile/konstantinos.karras/viz/AthensAirBnB2023Dashboard/AthensAirBnB2023Dashboard  
