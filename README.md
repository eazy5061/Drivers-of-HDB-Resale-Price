# Analysis of HDB Resale Flats Price from Jan 2017 to Dec 2024
[![made-with-python](https://img.shields.io/badge/Made%20with-Python-blue.svg)](https://www.python.org/)
[![Generic badge](https://img.shields.io/badge/STATUS-IN%20PROGRESS-yellow.svg)](https://shields.io/)

<img src="HDB flats.jpg" alt="Screenshot of dashboard" width="850" height="450">

<br>

## Project Goals
1. Start a end-to-end project, from scraping data, to cleaning, modelling, and deploying the model
2. To **identify** the drivers of HDB resale prices in Singapore.
3. To **scrape** and **engineer** additional features from online public datasets that might also influence resale prices
4. To **deploy** the model onto a web app, allowing for HDB resale prices prediction for different HDB features

<br>

## About the Data
The HDB resale price data was downloaded from [Data.gov.sg](https://data.gov.sg/datasets/d_8b84c4ee58e3cfc0ece0d773c8ca6abc/view), containing 197,012 resale transactions from 2017 to 2024.

## Introduction
The Housing & Development Board (HDB) is Singapore's public housing authority. They plan and develop Singapore's housing estates; building homes and transforming towns to create a quality living environment for all. 
<br>The purpose of this project is to delve the resale prices trends, the contributing factors and predictive models using data analysis and machine learning.

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

## EDA









</br>
<details>
  <summary>Click me</summary>
    
</details>

What you learned

What you'd change

Link to your LinkedIn
