# Welcome
I am an aspiring data analyst who has a passion in working with data to resolve problems and provide insights.

<br>

<br>

# Drivers of HDB Resale Price
[![made-with-python](https://img.shields.io/badge/Made%20with-Python-blue.svg)](https://www.python.org/)
[![Generic badge](https://img.shields.io/badge/STATUS-COMPLETED-green.svg)](https://shields.io/)
[![LinkedIn Connect](https://img.shields.io/badge/LinkedIn-Connect-blue)](https://www.linkedin.com/in/hongliang-tea/)

<img src="HDB flats.jpg" alt="Screenshot of dashboard" width="850" height="450">

<br>

## Project Goals
1. Start the project by scraping data, cleaning, modelling, and deploying the model
2. To **identify** the drivers of HDB resale prices in Singapore.
3. To **scrape** and **engineer** additional features from online public datasets that might also influence resale prices

<br>

## About the Data
The HDB resale price data was downloaded from [Data.gov.sg](https://data.gov.sg/datasets/d_8b84c4ee58e3cfc0ece0d773c8ca6abc/view), containing 197,012 resale transactions from January 2017 to December 2024.

<br>

## Data Scraping
The names of schools, supermarkets, hawkers, shopping malls, parks and MRTs were downloaded/scraped from [Data.gov.sg](https://data.gov.sg/) and fed through a function that uses [OneMap.sg](https://www.onemap.sg/main/v2/) api to get their coordinates (latitude and longitude) and postal code. These coordinates were then fed through other functions that use the geopy package to get the distance between locations. By doing this, the nearest distance of each amenity from each house can be computed, as well as the number of each amenity within a 2km radius of each flat.

<br>

## Data Formatting
From the Empathy Map, various infomation for location of flat with respective proximity to certain location will be essential for buyer decision.
Therefore to incorporate the Location factor into the existing data sets and to see the impact of the information to the resales flat.
Singapore location files was obtain from kaggle website('https://www.kaggle.com/'), which was perviously retrieved from one map Singapore website ('https://docs.onemap.sg/').
The address information which have the blk and street which can be utilised for the HDB dataset. The following information of data was not in tally with the HDB data sets and required to be modified.
The HDB data set street_name is using abbreviaton, but SGZip data set is using actual which is actual word.eg AVE vs Avenue, ST vs Street, RD vs Road, BK vs Buikit, TG vs Tanjong,...
The block and street_name are separate in the both dataset and this needs to combine for postal identify which can be link to coordinates.

<br>

## Exploratory Data Analysis
### Heatmap of Resale Price by Town and Flat Type
<img src="Heatmap of average resale price by town & flat type.jpg" alt="Screenshot of dashboard" width="800" height="520">

<br>

* The highest average resale price is an Executive Flat located in Queenstown; The lowest mean resale price is a 1 Room Flat in Bukit Merah.
* 1 Room Flats are only transacted in the town of Bukit Merah.
* Multi-Generation flats are sold in towns of Tampines, Yishun and Bishan.
* Central Area has the highest average resale price for the 5 Room Flat among the 26 towns.

<br>

## Number of flats sold
<b>By Town</b> 

<br>

<img src="Number of resale flats sold by Town.jpg" alt="Screenshot of dashboard" width="750" height="500">  

<b>From number of resale flats sold by town bar chart</b>

* The town having the highest number of resale flats sold is Sengkang .
* The town having the lowest number of resale flats sold is Bukit Timah.



<br>

<b>By Flat Type</b>

<br>

<img src="Number of flats sold by flat type.jpg" alt="Screenshot of dashboard" width="550" height="400"> 

<b>From the number of resale flats sold by flat type bar chart</b>

* The highest number of resale flats type sold is 4 room flat.
* The lowest number of resale flats sold is 1 Room flat (76 units) and Multi-Generation flat (80 units).

<br>

## Number of flats sold based on lease commence year
<img src="Number of flats sold by lease commence year.jpg" alt="Screenshot of dashboard" width="1100" height="600">

<br>

<b>From bar chart of number of resale flats sold per lease commence date (data is from past HDB resales transaction from Jan 2017 to Nov 2020)</b>
* Resale flats sold per lease commence date varies.
* Top 2 highest number of resale flats sold based on their lease commence years in 1985 and 2015. The latter could possibly because a lot of flats reached their minimum occupation period.

<br>

## Average resale price
<b>By Town</b> 

<br>

<img src="Average resale price by town.jpg" alt="Screenshot of dashboard" width="750" height="500">  

* Bukit Timah town has the highest average resale price while Yishun town has the lowest average resale price.
* Central region (Bukit Timah, Bishan, Bukit Merah, Central area and Queenstown) generally have higher average resale price among other towns.
* Bukit Timah has the highest median resale price while Ang Mo Kio has the lowest median resale price.
* The blue dotted line represents the nation-wide average resale price.
* Above the line means that the flats in that town is more expensive than the nation-wide average resale price.

<br>

<b>By Flat Type</b>

<img src="Average resale price by flat type.jpg" alt="Screenshot of dashboard" width="850" height="500">  

* Multi-generation flat type has the highest average resale price, while 1 room flat type has the lowest average resale price.
* There is not much significant difference between the average and median distributions for all flat types.

<br>

<b>By Storey Range</b>

<img src="Average resale price by Storey Range.jpg" alt="Screenshot of dashboard" width="850" height="500">  

* From the chart as the storey range increases, the resale prices also increases.

<br>

<b>By year and flat type</b>

<img src="Average resale price by year and flat type.jpg" alt="Screenshot of dashboard" width="800" height="1000">

* For 1 Room Flat to 5 Room Flat
Resale prices in 2018 and 2019 decreases as compared to year 2017. In 2020, the resale price increases again and for 4 and 5 Room the price overtakes the one in year 2017.
* For Executive Flat
Resale price fluctuates from 2017 to 2020. In year 2018, the resale price went up. It went down in 2019 and up again in 2020.
* For Multi-Generation Flat
Resale price initially increases from 2017 to 2019, but in 2020, the resale price goes below that of 2017.
<b>Conclusion:</b>
* There are similarities increasing trend of resale prices from year 2021 across all flat types.
* The reason for the decline in the resale prices from 1 room to executive flats in 2019 could be due to lesser demand during Covid19 pandemic.

<br>

# Relationships between Resale price and factors

<br>

<b>Relationship between Storey Range</b>

<img src="Relationship between Resale Price and Storey Range.jpg" alt="Screenshot of dashboard" width="850" height="600">

* R2 score of 0.9882 indicates that there is a very strong positive linear relationship between resale price and storey range. The P value is 0.0 which means that there is statistically significance correlation between the resale price and storey range. 
* Based on the scatter plot, we can derive that higher floor flats are sold at a higher resale price.

<br>

<b>Relationship between Floor Area</b>

<img src="Relationship between Resale Price and Floor Area.jpg" alt="Screenshot of dashboard" width="900" height="600">

* (R2) score of 0.9029 indicates that there is a very strong positive linear relationship between resale price and floor area. The P value is 0.0 which means that there is statistically significance correlation between the resale price and floor area.
* Based on the scatter plot, we can derive that larger area flats are sold at a higher resale price.

<br>

<b>Relationship between Flats Farther From Town</b> 

<img src="Relationship between flats further from town and Resale price.jpg" alt="Screenshot of dashboard" width="900" height="700">

* From this chart, we can see that the relationship is negative. Those flats that are farther from Dhoby Ghaut MRT station (Central) are having lower resale prices.

<br>

<b>Relationship between Distance from nearest Amenities</b>

<img src="Resale Price vs Distance from nearest Amenities.jpg" alt="Screenshot of dashboard" width="800" height="150">

* Most amenities (e.g., hawker, parks, malls, MRT and supermarkets) show a negative correlation with distance, meaning properties closer to these amenities are sold at higher resale prices.
* MRT stations have the strongest impact on resale prices, reflecting the importance of convenient public transport access.
* Unlike other amenities, distance from schools shows a weak positive correlation, suggesting proximity to schools may not significantly to influence the resale prices.

<br>

b>Relationship between numbers of amenities in 2KM radius</b>

<img src="Resale price vs distance from nearest amenities in 2km radius.jpg" alt="Screenshot of dashboard" width="800" height="150">

* Most amenities in 2KM radius show weak relationships with resale prices. Distance to hawker, parks, MRT stations, and malls appear to have a slightly positive effect on property prices, whereas the presence of schools and supermarkets may have slightly negative or negligible impact. 
* The results suggest that amenities play a role in property resale prices, but the influence is not very significant.

<br>

<b>Resale Price between Consumer Price Index (CPI)</b> 

<img src="Correlation between resales prices and consumer price index.jpg" alt="Screenshot of dashboard" width="800" height="500">

* Having the R2 score of 0.3304 indicates that there is a moderate positive linear relationship for the two variables and it seems that the consumer price index (CPI) does not affect much on the resale prices.

<br>

# Heatmap and Geolocation Map

<img src="Heat Map.jpg" alt="Screenshot of dashboard" width="600" height="400">

* From the heatmap, we can see that Sengkang & Punggol towns are very popular to buyers as that areas are very red.

<img src="Geolocation Map.jpg" alt="Screenshot of dashboard" width="800" height="500">

* The geolocation map shows the MRT/LRT stations, schools, shopping malls and HDB resale flats sold. 
* Sengkang and Punggol towns are popular to buyers could be due to accessible by LRT and a lot of schools and shopping malls nearby.

# Conclusion

* From this project, we managed to identify that the top 3 main drivers for the resale price of a HDB flat is the size, the storey and the location of the flat. Sizes and storey are identify as main driver as they have strong relationship with the resale prices which means that sizes or storey increase, the price will increase. As for location, we can see that flats that are nearer to Central Business District(CBD) areas are sold at higher resale prices. Buyers are willing to pay higher price for flats that are nearer amenities such as parks, hawker centers, MRT stations and malls, but if the amenities are out of the 2KM radius the influence is not very significant.

<br>

# What have I learnt and challenges met

* One of the achievement is the heatmap of the HDB resales transactions which indicate the number of transactions in that location. So the more red the area, the more transactions are done at that area. We can zoom in and out of the map to see the transactions more clearly, but was unable to show it in GitHub as it is in html format.

<br>

* The challenges for this project is that it has only 7 days duration before submission and the first 2 days is the selection of the topic for the project which I was still stuck on which topic shall I do.
* After decided the topic, I started off aimlessly as I felt that I am running out of time. After wasted sometime doing aimlessly, I decided to approach my trainer, Bishmer for advice. Managed to catch up on time and complete it within the schedule. Stress handling and time management is important.

<br>

Click to connect to my LinkedIn
<br>
[![LinkedIn Connect](https://img.shields.io/badge/LinkedIn-Connect-blue)](https://www.linkedin.com/in/hongliang-tea/)
