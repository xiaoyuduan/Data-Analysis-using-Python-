Using the Google Places API with a Database and
Visualizing Data on Google Map

In this project, we are using the Google geocoding API
to clean up some user-entered geographic locations of
university names and then placing the data on a Google
Map.

The first problem to solve is that the Google geocoding
API is rate limited to a fixed number of requests per day.
So if you have a lot of data you might need to stop and
restart the lookup process several times.  So we break
the problem into two phases.

In the first phase we take our input data in the file
(where.data) and read it one line at a time, and retrieve the
geocoded response and store it in a database (geodata.sqlite).
Before we use the geocoding API, we simply check to see if
we already have the data for that particular line of input.

Run the geoload.py program.   This program will read the input
lines in where.data and for each line check to see if it is already
in the database and if we don't have the data for the location,
call the geocoding API to retrieve the data and store it in
the database.

As of December 2016, the Google Geocoding APIs changed dramatically.
They moved some functionality that we use from the Geocoding API
into the Places API.  Also all the Google Geo-related APIs require an
API key. To complete this assignment without a Google account,
without an API key, or from a country that blocks
access to Google, you can use a subset of that data which is
available at:

http://py4e-data.dr-chuck.net/json

To use this, simply leave the api_key set to False in 
geoload.py.

This URL only has a subset of the data but it has no rate limit so
it is good for testing.

If you want to try this with the API key, follow the
instructions at:

https://developers.google.com/maps/documentation/geocoding/intro

and put the API key in the code.


Open where.html in a browser to see the locations.  You
can hover over each map pin to find the location that the
gecoding API returned for the user-entered input.  

