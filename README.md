# Profitable-App-Profiles

# Table of Contents
- [Objective](#objective)
- [Data Source](#data-source)
- [Project Stages](#project-stages)
- [Design & Mockup](#design--mockup)
- [Tools](#tools)
- [Data Exploration](#data-exploration)
- [Data Cleaning & Preparation](#data-cleaning--preparation)
  - [Objective](#Objective)
  - [Detecting Data Issues](#detecting-data-issues)
  - [Dropping Irrelevant Columns](#dropping-irrelevant-columns)
  - [Processing Steps in Excel](#processing-steps-in-excel)
  - [Output](#Output)
- [RFM Modeling with SQL Server](#rfm-modeling-with-sql-server)
  - [Purpose](#purpose)
  - [Key Steps](#key-steps)
  - [Output](#output)
- [Power BI Dashboard Development](#power-bi-dashboard-development)
  - [Objective](#objective)
  - [DAX Measures Created](#dax-measures-created)
  - [Dashboard Component](#dashboard-components)
- [Insight Extraction & Recommendations](#insight-extraction--recommendations)
  - [Findings](#findings)
  - [Recommendations](#recommendations)
- [Conclusion](#conclusion)

# Objective

Our aim in this project is to find mobile app profiles that are profitable for the App Store and Google Play markets. We're working as data analysts for a company that builds Android and iOS mobile apps, and our job is to enable our team of developers to make data-driven decisions with respect to the kind of apps they build. 

At our company, we only build apps that are free to download and install, and our main source of revenue consists of in-app ads. This means that our revenue for any given app is mostly influenced by the number of users that use our app. Our goal for this project is to analyze data to help our developers understand what kinds of apps are likely to attract more users.

# Data Source  

This project uses two publicly available datasets from Kaggle, containing app metadata from the Google Play Store and Apple App Store. These datasets were used to explore market trends, identify popular app genres, and estimate potential profitability.

**1. Google Play Store Dataset: You can download from [this link](https://www.kaggle.com/datasets/lava18/google-play-store-apps)**
**2. Apple App Store Dataset: You can download from [this link](https://www.kaggle.com/datasets/ramamet4/app-store-apple-data-set-10k-apps)**

# Opening and Exploring the Data

As of September 2018, there were approximately 2 million iOS apps available on the App Store, and 2.1 million Android apps on Google Play.

![img](https://s3.amazonaws.com/dq-content/350/py1m8_statista.png) 

Source: [Statista](https://www.statista.com/statistics/276623/number-of-apps-available-in-leading-app-stores/)

Collecting data for over four million apps requires a significant amount of time and money, so we'll try to analyze a sample of data instead. To avoid spending resources with collecting new data ourselves, we should first try to see whether we can find any relevant existing data at no cost. Luckily, these are two data sets that seem suitable for our purpose:

- [A data set](https://www.kaggle.com/lava18/google-play-store-apps) containing data about approximately ten thousand Android apps from Google Play. You can download the data set directly from [this link](https://dq-content.s3.amazonaws.com/350/googleplaystore.csv).
- [A data set](https://www.kaggle.com/ramamet4/app-store-apple-data-set-10k-apps) containing data about approximately seven thousand iOS apps from the App Store. You can download the data set directly from [this link](https://dq-content.s3.amazonaws.com/350/AppleStore.csv).

Let's start by opening the two data sets and then continue with exploring the data.

```python
from csv import reader

### The Google Play data set ###
opened_file = open('googleplaystore.csv', encoding = 'utf-8')
read_file = reader(opened_file)
android = list(read_file)
android_header = android[0]
android = android[1:]

### The App Store data set ###
opened_file = open('AppleStore.csv', encoding = 'utf-8')
read_file = reader(opened_file)
ios = list(read_file)
ios_header = ios[0]
ios = ios[1:]
```
