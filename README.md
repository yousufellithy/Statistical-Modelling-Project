# Final-Project-Statistical-Modelling-with-Python

## Project/Goals
The goal is to retrieve all the bike stations in a city (I chose Toronto). For each bike station, we get nearby parks from two sources, Foursquare and Yelp. This is done by connecting to their APIs. The final model is to answer our question: Is there a correlation between the distance and number of parks to planes of latitudes (of bikes)?  Independents: how far to the closest park according to Foursquare/yelp and how many parks are found in a radius of 500m according to Foursquare/yelp, dependant: latitude


## Process
Step 1: retrieved the location (latitude and longitude) and how many free bikes there were for each bike station using the citybike API.
Step 2: for each bike station location, I found how many parks there were in a 500m radius and how far the closest park is to each station. I got this information from FourSquare and Yelp's APIs (I only got 10 from Yelp because I kept running out of API tokens. 
Step 3: combined the dataframe foursquare and Yelp
step 4: created a linear regression model to see if there were correlations.

QA: 
1. I checked some of the longitudes and latitudes randomly in the data to make sure they were valid and in the city (Toronto).
2. Checking to see if there’s a network in the code
4. The API fetch was during the day at a time when people rent bikes, so that it can be accurate because that’s when people usually rent bikes but keep in mind because the weather is colder, the data can heavily change in the summer
5. I'm dropping the last row as it seems to be a huge outlier, potentially a glitch because the max distance should be 500 as observed with all other rows. This will need to be looked at further, it will not be in the regression model either as it could skew the results.
6. The row names were also changed:
merged_df.rename(columns={'Number of Parks found_x': 'Number of Parks found (FourSquare)', 'Distance to Closest Park_x': 'Distance to Closest Park (FourSquare)', 'Number of Parks found_y': 'Number of Parks found (Yelp)', 'Distance to Closest Park_y': 'Distance to Closest Park (Yelp)'}, inplace=True)
7. I also filtered all the results from the FourSquare and Yelp APIs to only use the distance and filter out the rest. 

merged_df = merged_df[merged_df['Distance to Closest Park (Yelp)'] <= 501] 


## Results
I got more data from Foursquare compared to Yelp, after creating the model.  The only correlation found was to the Distance to the Closest Park from (FourSquare), which had a pvalue of 0.053 (rounded down would be 0.05) and the R-squared: 0.692 which is strong enough. The rest seem to indicate that they have no effect on the planes of latitude of bike stations. 

## Challenges 
The Foursquare and Yelp API retrieval process was extremely difficult for me because of some of the complexity in it. 

## Future Goals
If I had more time I would spend some money to get more credit on Yelp's API so I can retrieve as many searches as I want. Additionally, I would examine more comparisons of what kind of data comes from FourSquare as opposed to Yelp. Compiling and using more data would make a more reliable model. 
