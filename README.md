# Final-Project-Statistical-Modelling-with-Python

## Project/Goals
The goal is to retrieve all the bike stations in a city (I chose Toronto). For each bike station, we get nearby parks from two sources, Foursquare and Yelp. This is done by connecting to their APIs.


## Process
Step 1: retrieved the location (latitude and longitude) and how many free bikes there were for each bike station using the citybike API.
Step 2: for each bike station location, I found how many parks there were in a 500m radius and how far the closest park is to each station. I got this information from FourSquare and Yelp's APIs (I only got 10 from Yelp because I kept running out of API tokens. 
Step 3: combined the dataframe foursquare and Yelp
step 4: created a linear regression model to see if there were correlations.


## Results
I got more data from Foursquare compared to Yelp, after creating the model, there were no correlations at all between the location of bike stations and the location of parks. All of the p-values were much higher than 0.05.

## Challenges 
The Foursquare and Yelp API retrieval process was extremely difficult for me because of some of the complexity in it. 

## Future Goals
If I had more time I would spend some money to get more credit on Yelp's API so I can retrieve as many searches as I want. Additionally, I would examine more comparisons of what kind of data comes from FourSquare as opposed to Yelp.  
