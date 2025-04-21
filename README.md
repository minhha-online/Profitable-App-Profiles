# Profitable App Profiles for the App Store and Google Play

## Overview

This project analyzes data from the Google Play Store and Apple App Store to identify types of apps that are most likely to be profitable. The focus is on **free** and **English-language** apps, using user engagement metrics (like installs and ratings) as proxies for popularity and success.

---

## Objectives

- Explore and clean two large app datasets
- Filter for high-quality, relevant apps (free, English)
- Analyze popular app genres across platforms
- Estimate profitability using user ratings and install counts
- Provide strategic recommendations for app development

---

## Data Sources

### 1. Google Play Store
- [Google Play Store Apps on Kaggle](https://www.kaggle.com/datasets/lava18/google-play-store-apps)
- ~10,000 apps with fields like name, category, rating, installs, price

### 2. Apple App Store
- [Apple App Store (10K) on Kaggle](https://www.kaggle.com/datasets/ramamet4/app-store-apple-data-set-10k-apps)
- ~7,000 apps with fields like name, genre, user rating count, price

> Only **free** and **English-language** apps are included to ensure fair comparison.

---

## Data Cleaning Steps

- Removed erroneous rows and duplicates
- Retained apps with the highest number of reviews per name
- Filtered out non-English and paid apps
- Standardized install counts and genre fields

---

## Key Insights

- iOS apps in **Education** and **Productivity** categories show strong, consistent engagement
- Android apps in **Books & Reference** and **Tools** categories provide good growth opportunities after filtering out dominant apps
- Free apps dominate both stores — freemium or ad-supported models are most viable
- iOS users show greater willingness to engage with high-quality, feature-rich apps

---

## Recommendations

- Target **Education** and **Productivity** apps for iOS
- Target **Utility** or **Reference** apps for Android
- Use **freemium models** with premium add-ons or in-app purchases
- Avoid oversaturated genres like Social or Games unless highly differentiated

---

## Project Files

- [`Mission350Solutions_Reviewed.ipynb`](./Mission350Solutions_Reviewed.ipynb): Final cleaned notebook with analysis
- [`README.md`](./README.md): Project overview and instructions

