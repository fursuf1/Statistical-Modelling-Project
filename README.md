# Bike Share Station Analysis using Statistical Modeling

## Project Overview

This project aims to analyze the positioning and size of bike-share stations in relation to points of interest in the city of Dublin. The data for bike-share stations is sourced from citybik.es, while points of interest data is collected from Yelp and Foursquare (FSQ) APIs.

## Process

1. **API Data Retrieval**: The initial step involves establishing API connections with the three data providers (citybik.es, Yelp, and Foursquare). Sample analysis was performed on the API responses to identify relevant fields and understand data manipulation requirements for individual bike-share stations.

2. **Scaling to All Stations**: The methodology developed in the first step was scaled to apply to all bike stations, ensuring that insights drawn are representative of the entire dataset.

3. **Data Merging and Summary**: Outputs from the previous step were summarized and merged to create a comprehensive database containing relevant information about bike stations, Yelp data, and FSQ data.

4. **Analysis and Model Creation**: Using the merged dataset, an exploratory analysis was conducted to establish relationships between variables. A regression model was developed to quantitatively define the relationship between bike station size and the volume of nearby points of interest.

## Results and Challenges

For both Yelp and FSQ APIs, each bike station returned the maximum of 50 points of interest. However, due to variations in the categories of points of interest, the analysis was narrowed down to examine the relationship between the number of pubs and cafes and bike station size. The rationale behind this was that a higher number of pubs and cafes might indicate a greater need for transportation in that area. The analysis suggested a weak inverse relationship (correlation coefficient = -0.3) and a linear regression R-squared value of 0.1.

Challenges arose in comparing the APIs. Yelp had fewer ratings available compared to FSQ, and it returned a limited number of unique values even when searching for common categories like "restaurants." This discrepancy in data completeness might be attributed to Yelp's popularity in the specific region. Both APIs were limited to returning 50 responses per request, leading to variations in responses for the same category due to the cap. This variability introduced inaccuracies in the analysis. A potential solution could be refining the API requests by reducing the radius and focusing on specific categories to obtain a more complete dataset.

## Future Goals

Given more time, refining the API calls to reduce the radius and exploring ways to bypass or minimize the response cap would be a priority. Additionally, analyzing bike station density along with size could provide insights into concentration patterns. The analysis could also benefit from more localized queries to yield higher-quality datasets.
