# BerkelyHaasCarEvaluation
AI ML Berkely Hass Module 11 assignment for Used car sales data analysis using CRISP-DM

# Factors Influencing Used Car Valuation
This is  Berkely Haas Module 11 assignment for Used car sales data analysis using CRISP-DM.

## Problem Understanding
Ojective is to scrutinize and interpret a dataset of used car sales to determine the primary elements that influence their market value. The aim is to pinpoint the attributes that either raise or lower a car's price, thereby offering actionable insights and guidance to a client, who operates a used car dealership, about the preferences and priorities of buyers in the pre-owned car market.


## Data 
#### Data Source and Description
This dataset is a subset  of a 3-million records source from Kaggle. The size is reduced to 426K car sales information to accommodate the  processing power of a personal or laptop computer. It does not come with data descriptions, and the dataset's source is no longer traceable. Here is my understanding of the dataset. All transactions are assumed to have taken place in 2022.

This dataset provides a comprehensive range of attributes for each used car sales transaction, which can be instrumental in understanding the factors influencing car prices. Here's a brief overview of how each attribute might impact your analysis:

**Dataset ID**: A unique identifier for each transaction, useful for data management but not directly influencing price.

**Region**: Location can affect prices due to regional demand, economic conditions, and availability.

**Price**: The dependent variable you are trying to predict or explain.

**Year**: The model year often correlates with a car's value; newer cars tend to be more expensive.

**Manufacturer and Model**: Brand and specific model can significantly impact price due to perceived quality, reliability, and prestige.

**Condition**: The condition of a car (e.g., new, excellent, fair) is a key determinant of its value.

**Cylinders**: This may indicate engine size and performance, affecting both the car’s desirability and price.

**Fuel**: The type of fuel (e.g., gas, diesel, electric) can influence cost, especially as environmental concerns and fuel prices vary.

**Odometer**: Mileage is a critical factor; higher mileage usually decreases a car's value.

**Title Status**: Clean titles are preferable, while issues like liens or salvage status can drastically reduce a car’s price.

**Transmission**: Preferences can vary by market; automatic transmissions are generally more popular, but manual can be valued in certain models or regions.

**VIN**: Primarily for record-keeping, but can be used to verify car history which might influence value.

**Drive**: The type of drive (4wd, fwd, rwd) can impact a car’s desirability based on performance and utility.

**Size**: Vehicle size (full-size, mid-size, etc.) can affect price due to differing consumer needs and preferences.

**Type**: Different types of vehicles (sedan, SUV, pick-up, etc.) cater to various market segments and demand.

**Paint Color:** While often a minor factor, color can influence buyer preferences and resale value.

**State**: The state of the transaction can affect prices due to regional market differences, tax rates, and demand patterns.

By analyzing these attributes, patterns and relationships that can help in advising the used car dealership on what aspects are most valued in their market can be uncovered.

#### Data Transformation
In the preliminary phase of examining the used car dataset, a significant portion of the records – about 75% of the 426,000 entries – were identified as unsuitable for analysis due to issues such as duplication and data inconsistencies. Key anomalies included:

Duplicates: A substantial 40% of the entries had repeating Vehicle Identification Numbers (VINs), indicating duplicate records.

Price Irregularities: There were instances of extreme pricing anomalies, such as a 2005 Toyota Tundra listed at an unrealistic price of 3.7 billion dollars.

Condition and Age Mismatch: Cars labeled as 'new' exhibited an average age of 6.5 years with 54,000 miles on the odometer, which contradicts the typical expectations for a 'new' vehicle.

The data was carefully transformed to eliminate both obvious and subtle discrepancies, ensuring a more accurate and reliable dataset for the subsequent exploratory analysis. 


## Vehicle Age Versus Selling Price
<img src="https://github.com/RashmiTechie/BerkelyHaasCarEvaluation/tree/main/images/age_vs_price.png">






