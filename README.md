# Default repository template

## Title

## Abstract
A max 150-word description of the project question or idea, goals, dataset used. What story you would like to tell and why? What's the motivation behind your project?

## Research questions
A list of research questions you would like to address during the project. 

## Dataset
The main dataset we will be using is Yelp Dataset (link) — collection containing businesses, reviews, and user data. The dataset is freely available for download and has a size of 8.65GB uncompressed and 4.04GB compressed. As per documentation, “[e]ach file is composed of a single object type, one JSON-object per-line.”
Due to the dataset's large size, it may be reduced by assuming a statistical model for the data, or training can occur in batches of equal size to parallelize the training and cover more parts of the dataset.
The main files and properties we will be focusing on for our project are:
•	business.json
File contains business data including location data, attributes, and categories. Specifically (prospectively) fields “city”, “latitude”, and “longitude” would be used for the project. 
•	review.json
As per documentation: “[c]ontains full review text data including the user_id that wrote the review and the business_id the review is written for.”
Fields “stars”, “data”, “text”, and an emotive category (i.e., “useful”, “funny”, etc.) would be mainly utilized for the project.
To supplement the main dataset, we will gather auxiliary datasets using web scraping from weather websites. Although we have not yet chosen any specific datasets or web scraping services, sources such as:
•	https://weather.com/ via BeautifulSoup Python extension (link) OR OpenWeatherMap API (link)
•	https://www.visualcrossing.com/weather-api
seem to provide a feasible and free solution. Since the original data is largely reduced to the US, by using the name of the city (potentially state in the case of "twin cities") and the time of the review, we should be able to acquire needed weather parameters such as temperature, humidity, and characteristics like "windy", "cloudy", "sunny", etc. without major issues.


## A tentative list of milestones for the project
Add here a sketch of your planning for the coming weeks. Please mention who does what.

## Documentation
This can be added as the project unfolds. You should describe, in particular, what your repo contains and how to reproduce your results.
