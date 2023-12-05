# Factors Influencing Used Car Valuation
This is  Berkely Hass Module 11 assignment for Used car sales data analysis using CRISP-DM.

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

## Car Sales Price by Car Age
<img src="https://github.com/chihming-chen/BerkeleyHaas-car-sales-EDA/blob/main/images/age_vs_price.png">

## Classic, Vintage, and Antique Cars
As can be seen above, used car prices decrease as they age until they become collectible classic or vintage cars. The prices of classic, vintage, and antique cars are known to depend on the scarcity of these cars. Since the dataset does not provide that information, they are excluded from this exploratory analysis.

## Average Sale Price by Car Manufacturers
<img src="https://github.com/chihming-chen/BerkeleyHaas-car-sales-EDA/blob/main/images/price_by_manufacturer.png">

## <a id='truck'></a>Average Sale Price by Car Types
<img src="https://github.com/chihming-chen/BerkeleyHaas-car-sales-EDA/blob/main/images/price_by_type.png">

## Average Sale Price by Fuel Types
<img src="https://github.com/chihming-chen/BerkeleyHaas-car-sales-EDA/blob/main/images/price_by_fuel.png">

## Average Sale Price by Drive Types
<img src="https://github.com/chihming-chen/BerkeleyHaas-car-sales-EDA/blob/main/images/price_by_drive.png">

## What Drives the Price of a Used Car?

### Key Insights
The dataset contains 16 attributes of a car sales transaction, including the features and specs of the car and where the transaction occurred. All attributes affect the price of a used car to some extent. Six factors were identified as key influencers on the sale price - the Ferrari prestige, diesel engine premium, front-wheel-drive disadvantage, cylinder horsepower, and age/mileage wear-and-tear. 

### Quantitative Analysis
Several linear regression models with LASSO regularization were built for the quantitative analysis after painstaking data cleansing. These factors were identified as key influencers on the price of used cars. In order of importance: 
1. The Ferrari Brand: Ferrari cars were sold at prices significantly higher. On average, a Ferrari is priced $147,250 higher than other brands, with all other car features and conditions being identical.
2. Diesel engine premium: Cars equipped with a diesel engine tend to have a higher value, approximately $10,340 more than cars without this feature. However, this may not be the direct cause of the car's value but a dependent feature of a truck that is worth more on average.
3. Drive Type: Front-wheel drive cars have a slightly lower average price than 4-wheel or rear-wheel drive counterparts. When other features remain constant, a front-wheel-drive car was sold for $4,160 less.
4. Cylinder's horsepower: Each additional cylinder in a car contributes approximately $2,143 to the car's price when other factors remain constant. More cylinders usually translate to a higher horsepower and make a car more valuable. Since the dataset does not come with the horsepower specs of cars, the number of cylinders becomes a good approximator.
5. Age of the Car: On average, the price of a car reduces by $1,026 for each year it ages, assuming other features remain constant. Please note this is an average number over the course of the life of a car. The depreciation of a car's price is much faster in the first year.
6. Odometer Reading: A car's value decreased by $0.06 for each mile driven, much less than I had expected. I suspect some dependent factors or uncaught data anomalies have yet to be uncovered.

## Performace of the Estimator
The chosen estimator uses these six factors to estimate the value of a used car, excluding classic, vintage, or antique cars. On average, it has a margin of error of 36%. In the $8,000 to $40,00 range, the model's forecasting sweet spot has a significantly improved margin of error of 24%. 
<p><img src="https://github.com/chihming-chen/BerkeleyHaas-car-sales-EDA/blob/main/images/6_vs_kde_modified.png"></p>
The forecasts or predictions (the green dots) outside of the outermost contour are almost certainly prediction outliers and should not be trusted. As the forecasts land more toward and within the innermost contour, the higher probability they are closer to the actual sales prices. If it were not for the remaining data anomalies in the dataset, the accuracy of the model would be higher. The lower price range contributes out of proportion to the percentage error rates. We should view the "Actual" price with many grains of salt due to its low data quality. Many data outliers are spotted and removed during the data cleansing process. However, anomalies lying between extreme ends prove to be very challenging to uncover and remove.
<p><img src="https://github.com/chihming-chen/BerkeleyHaas-car-sales-EDA/blob/main/images/enhanced_6_actual_vs_predicted.png"></p>
<p>Another more complex model using 15 factors, including the transmission (manual/automatic), and type of car (truck, sedan, etc) only improves the margin of error by 2.6%. This may also indicate the limitation of the chosen model. More complex models alongside improved data quality should be explored for better forecasting accuracy.
</p>

### Other Factors and Considerations

Other than the factors identified above, the car's condition, title status, and other features are believed to affect a car's price. However, due to quality issues and anomalies in the dataset, they are not used to make inferences or forecasts. For example, the dataset's average age of 'new' cars is 6.5 years old, with 54k odometer readings. Most likely, the classification of the condition as 'new' is incorrect in many cases. Those data anomalies had to be removed, and the conditions of vehicles could not be trusted and had to be ignored. Some unmeasured factors, such as horsepower and scarcity of vintage and antique cars, are believed to impact used car prices.
