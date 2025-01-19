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
* There is not much significant difference in the average and median distributions for all flat types.

<br>

<b>By Storey Range</b>

<img src="Average resale price by Storey Range.jpg" alt="Screenshot of dashboard" width="850" height="500">  
 
<details>
  <summary>Click me</summary>
    
</details>

What you learned

What you'd change

Link to your LinkedIn
