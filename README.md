# Bike Share Station Analysis using Statistical Modeling

## Project Overview

This project aims to analyze the positioning and size of bike-share stations in relation to points of interest in the city of Dublin. The data for bike-share stations is sourced from citybik.es, while points of interest data is collected from Yelp and Foursquare (FSQ) APIs.

## Process

1. **API Data Retrieval**: The initial step involves establishing API connections with the three data providers (citybik.es, Yelp, and Foursquare). Sample analysis was performed on the API responses to identify relevant fields and understand data manipulation requirements for individual bike-share stations.

2. **Scaling to All Stations**: The methodology developed in the first step was scaled to apply to all bike stations, ensuring that insights drawn are representative of the entire dataset.

3. **Data Merging and Summary**: Outputs from the previous step were summarized and merged to create a comprehensive database containing relevant information about bike stations, Yelp data, and FSQ data.

4. **Analysis and Model Creation**: Using the merged dataset, an exploratory analysis was conducted to establish relationships between variables. A regression model was developed to quantitatively define the relationship between bike station size and the volume of nearby points of interest.

## Results and Challenges

### Regression Model Results

The regression model demonstrates exceptional accuracy and a strong goodness of fit, affirming a robust relationship between Foursquare ratings and Yelp ratings:

- **Mean Squared Error (MSE)** is remarkably low, indicating highly accurate predictions.
- The **R-squared value** of approximately 0.993 signifies that around 99.3% of the variability in Yelp ratings can be effectively explained by Foursquare ratings.
- These impressive metrics underscore a significant correlation between Foursquare ratings and Yelp ratings within the scope of this analysis.

### Considerations and Further Investigation

However, it is vital to approach these findings with careful consideration and promote further investigation:

- Ensuring data quality involves validating the integrity of the datasets and addressing potential outliers or anomalies that could affect the analysis's reliability.
- The importance of avoiding potential sources of data leakage, which could artificially enhance model performance, cannot be overstated.
- Moreover, it's important to acknowledge that this analysis is grounded in the specific characteristics and limitations of the dataset. Consequently, the model's applicability and generalizability to other scenarios should be approached with cautious optimism.

### Yelp and FSQ API Analysis

Additionally, when examining the results and challenges arising from the Yelp and FSQ APIs:

- Both APIs yielded a maximum of 50 points of interest for each bike station. However, due to variations in point of interest categories, the analysis was focused on the correlation between the count of pubs and cafes and bike station size. This was motivated by the potential need for increased transportation in areas with more eateries. The analysis indicated a weak inverse relationship (correlation coefficient = -0.3) and an R-squared value of 0.1 from the linear regression model.
- Challenges emerged when comparing the APIs. Yelp exhibited fewer ratings compared to FSQ, and it consistently returned a limited number of unique values, even for broad categories such as "restaurants." This data discrepancy may stem from Yelp's regional popularity. Both APIs were constrained to 50 responses per request, leading to variations in responses for the same category due to the response cap. This variation introduced inaccuracies in the analysis. A potential solution would involve refining API requests by narrowing the radius and focusing on specific categories to achieve a more comprehensive dataset.

## Future Goals

Given more time, refining the API calls to reduce the radius and exploring ways to bypass or minimize the response cap would be a priority. Additionally, analyzing bike station density along with size could provide insights into concentration patterns. The analysis could also benefit from more localized queries to yield higher-quality datasets.
