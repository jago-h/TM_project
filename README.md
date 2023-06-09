# Feeling Under the Weather and Restaurant Rating Tendency: A Tentative NLP Research 

## Authors
Jago Hanuszewicz, Kengo Omi, Stanislav Sauliunas, Veronika Sitnova 

## Abstract
Our project aims to explore the influence of weather on people's sentiments when writing restaurant reviews on Yelp. Numerous studies have shown that people’s moods can be affected by weather(Denissen et al., 2008; Keller et al., 2005; Klimstra et al., 2011). When people write reviews for restaurants, there could be influences as well. We would like to understand the correlation between weather conditions and the emotions reflected in the written reviews. By examining this relationship, we can gain valuable insights into consumer behavior and decision-making.

We will use dataset released by Yelp, containing details from the reviews, reviewers, and the restaurants. Conveniently, the location of the restaurants and the timestamps of the reviews will enable us to scrap historical weather data. We will then investigate if different weather pattern would generate different sentiments in the reviews.

## References
* Denissen, J. J. A., Butalid, L., Penke, L., & van Aken, M. A. G. (2008). The effects of weather on daily mood: a multilevel approach. Emotion (Washington, D.C.), 8(5), 662–667. https://doi.org/10.1037/A0013497
* Keller, M. C., Fredrickson, B. L., Ybarra, O., Côté, S., Johnson, K., Mikels, J., Conway, A., & Wager, T. (2005). A warm heart and a clear head. The contingent effects of weather on mood and cognition. Psychological Science, 16(9), 724–731. https://doi.org/10.1111/J.1467-9280.2005.01602.X
* Klimstra, T. A., Frijns, T., Keijsers, L., Denissen, J. J. A., Raaijmakers, Q. A. W., van Aken, M. A. G., Koot, H. M., van Lier, P. A. C., & Meeus, W. H. J. (2011). Come rain or come shine: individual differences in how weather affects mood. Emotion (Washington, D.C.), 11(6), 1495–1499. https://doi.org/10.1037/A0024649
 

## Research questions
* How does the weather affect the review ratings of restaurants?
    - Is there any correlation between the mood of a review and its final grade?
    - How are the emotional sentiments affected by the weather conditions?
    - To what extend the correlation appear?
    - What about the areas of mostly 'bad' or 'good' weather?

## Dataset
The main dataset we will be using is Yelp Dataset ([link](https://www.yelp.com/dataset/documentation/main)) — collection containing businesses, reviews, and user data. The dataset is freely available for download and has a size of 8.65GB uncompressed and 4.04GB compressed. As per documentation, “[e]ach file is composed of a single object type, one JSON-object per-line.”

Due to the dataset's large size, it may be reduced by assuming a statistical model for the data, or training can occur in batches of equal size to parallelize the training and cover more parts of the dataset.
The main files and properties we will be focusing on for our project are:

* business.json <br>
File contains business data including location data, attributes, and categories. Specifically (prospectively) fields “city”, “latitude”, and “longitude” would be used for the project. 

* review.json <br>
As per documentation: “[c]ontains full review text data including the user_id that wrote the review and the business_id the review is written for.”

Fields “stars”, “data”, “text”, and an emotive category (i.e., “useful”, “funny”, etc.) would be mainly utilized for the project.
To supplement the main dataset, we will gather auxiliary datasets using web scraping from weather website. We decided on the following source:

* Open-Meteo Historical Weather API ([link](https://open-meteo.com/en/docs/historical-weather-api)). 

Where we can access a wide range of meteorological data, such as precipitation, wind speed, temperature 2m above the ground, cloudcover, and so on. We will do look for the weather data for the corresponding coordinates to enhance the comprehensiveness and credibility of our analysis.

Since the original data is largely reduced to the US, by using the name of the city (potentially state in the case of "twin cities") and the time of the review, we should be able to acquire needed weather parameters without major issues.


## A tentative list of milestones for the project
1. Github repository set up
2. YELP dataset loaded successfully
3. North America weather data for the timespan of the reviews scraped
4. A workable dataset for the weather created
5. Baseline model initiated to predict ratings/review sentiment based on weather data
6. Baseline model trained and evaluated
7. Potential additional parameters added (might include more information apart from the review text; for example, user’s total reviews and fans count to give a higher weight to the review)
8. Tuned model trained and evaluated
9. Model tested with new data
10. Analyse the resuls, create the presentation and final report

## Documentation
Our repo contains 3 notebooks with general data analysis:  
1. YELP data analysis (analysis.ipynb)
2. Weather scraping (weather_scraping.ipynb)
3. PyProcess analysis of reviews sentiment and weather (PyProcess.ipynb)

Futherly, there is a file with review pre-processing code and sentiment_analysis folder, containing the sentiment analysis code of 3 different methods:  
1. VADER Sentiment
2. Hedonometer 
3. TextBlob

Finally, in order to work on the data that we did, you have to follow the consequtive steps:  
1. reviews -> download the data using the Yelp Dataset ([link](https://www.yelp.com/dataset/documentation/main)); the dataset is freely available for download and has a size of 8.65GB uncompressed and 4.04GB compressed; “[e]ach file is composed of a single object type, one JSON-object per-line.”
2. weather -> follow the git repo ([link](https://github.com/m0rp43us/openmeteopy)); install with the following:  
```bash
git clone https://github.com/m0rp43us/openmeteopy
cd openmeteopy-main/
pip3 install .
```  
then use our code from `weather_scraping.ipynb`, where you can get the weather data for a specific coordinates and date of each review.

## Report
A short project report in the pdf format can be found the WrittenReport.pdf file.
