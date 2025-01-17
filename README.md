# Analysis of HDB Resale Flats Price from Jan 2017 to Dec 2024
[![made-with-python](https://img.shields.io/badge/Made%20with-Python-blue.svg)](https://www.python.org/)
[![Generic badge](https://img.shields.io/badge/STATUS-IN%20PROGRESS-yellow.svg)](https://shields.io/)

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
The names of schools, supermarkets, hawkers, shopping malls, parks and MRTs were downloaded/scraped from [Data.gov.sg](https://data.gov.sg/) and Wikipedia and fed through a function that uses [OneMap.sg](https://www.onemap.sg/main/v2/) api to get their coordinates (latitude and longitude). These coordinates were then fed through other functions that use the geopy package to get the distance between locations. By doing this, the nearest distance of each amenity from each house can be computed, as well as the number of each amenity within a 2km radius of each flat.

<br>

## Data Formatting
From the Empathy Map, we know that various infomation for location of flat with respective proximity to certain location will be essential for buyer decision.
Thus we need to incorporate the Location factor into the existing data sets, to see the impact of the information to the resales flat.
Singapore location files was obtain from kaggle website('https://www.kaggle.com/'), which was perviously retrieved from one map Singapore website ('https://docs.onemap.sg/').
The address information which have the blk and street which can be utilised for the HDB dataset. The following information of data was not in tally with the HDB data sets and required to be modified.
The HDB data set street_name is using abbreviaton, but SGZip data set is using actual which is actual word.eg AVE vs Avenue, ST vs Street, RD vs Road, BK vs Buikit, TG vs Tanjong,...
The block and street_name are separate in the both dataset and this needs to combine for postal identify which can be link to coordinates.

<br>

## Exploratory Data Analysis
### Pivot table by town, flat type and resale prices
<img src="Pivot Table.png" alt="Screenshot of dashboard" width="850" height="480">

## Number of flats sold
<b>By Town</b> &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<b>By Flat Type</b>
<br>
<img src="Number of flats sold by town.png" alt="Screenshot of dashboard" width="350" height="300"> <img src="Number of flats sold by flat type.png" alt="Screenshot of dashboard" width="350" height="300">  
* From number of resale flats sold by town bar chart, the town having the highest number of resale flats sold is Sengkang and the town having the lowest number of resale flats sold is Bukit Timah.
* From the number of resale flats sold by flat type bar chart, the highest number of resale flats type sold is 4 room flat. The lowest number of resale flats sold is 1 Room flat (76 units) and Multi-Generation flat (80 units).

<br>

## Number of flats sold based on lease commence year
<img src="Number of flats sold by lease commence year.png" alt="Screenshot of dashboard" width="350" height="300">

<br>

<b>From bar chart of number of resale flats sold per lease commence date (data is from past HDB resales transaction from Jan 2017 to Nov 2020),</b>
* Resale flats sold per lease commence date varies.
* Top 2 highest number of resale flats sold based on their lease commence years in 1985 and 2015. The latter could possibly because a lot of flats reached their minimum occupation period.

<br>

## Average resale price








</br>
  
<details>
  <summary>Click me</summary>
    
</details>

What you learned

What you'd change

Link to your LinkedIn
