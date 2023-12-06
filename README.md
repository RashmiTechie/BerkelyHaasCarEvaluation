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

The observed trend indicates a decline in used car prices with increasing age, up until they reach the status of collectible classics or vintage vehicles. Given the significant influence of scarcity on the value of classic, vintage, and antique cars, and the absence of scarcity data in the dataset, these categories of vehicles have been omitted from the current exploratory analysis.

## Average Sale Price by Car Manufacturers
<img src="https://github.com/RashmiTechie/BerkeleyHaas-car-sales-EDA/tree/main/images/price_by_manufacturer.png">

## <a id='truck'></a>Average Sale Price by Car Types
<img src="https://github.com/RashmiTechie/BerkelyHaasCarEvaluation/tree/main/images/price_by_type.png">

## Average Sale Price by Fuel Types
<img src="https://github.com/RashmiTechie/BerkelyHaasCarEvaluation/tree/main/images/price_by_fuel.png">

## Average Sale Price by Drive Types
<img src="https://github.com/RashmiTechie/BerkelyHaasCarEvaluation/tree/main/images/price_by_drive.png">


## Summary of Crucial Findings and Quantitative Analysis
The dataset comprises 16 attributes related to used car sales transactions, including car specifications and transaction locations. Each attribute influences the car's sale price to varying degrees. Notably, six factors emerged as primary determinants of sale price: the prestige associated with the Ferrari brand, the added value of diesel engines, the impact of drive type (specifically front-wheel drive), the contribution of cylinder horsepower, and the effects of age and mileage on vehicle wear-and-tear.
## Analysis
Through rigorous data cleansing, several linear regression models featuring LASSO regularization were developed. These models pinpointed the following key influencers on used car prices, listed in order of their impact:

1.Diesel Engine Premium: Diesel-powered cars generally commanded an additional $10,340 in value compared to their non-diesel counterparts. This premium might reflect the inherent value of trucks, which commonly feature diesel engines.
Drive Type: Front-wheel-drive vehicles typically sold for $4,160 less than those with 4-wheel or rear-wheel drive, all else being equal.

2.Odometer Reading: The value of a car decreased by just $0.06 for each additional mile, a lower rate than anticipated. This finding suggests possible underlying factors or unrecognized data anomalies.

3.Cylinder Horsepower: Each additional cylinder added roughly $2,143 to a car’s price, under constant conditions. This reflects the correlation between the number of cylinders, increased horsepower, and the car's overall value.
Car Age: A car depreciates by an average of $1,026 annually, with the caveat that depreciation is most rapid in the first year.

4.Ferrari Brand: Cars from Ferrari fetched considerably higher prices, averaging $147,250 more than other brands when all other features are equal.

## Estimator Performance
The performance analysis of the estimator reveals insights into the robustness and accuracy of the model in predicting used car prices, taking into account the identified key factors.
The selected estimator, focusing on the six identified key factors, is employed to determine the value of used cars, specifically excluding classic, vintage, or antique vehicles.
On average, this model exhibits a margin of error of 36%. However, its accuracy improves considerably within the price range of $8,000 to $40,000. In this specific segment, the model demonstrates a more refined margin of error at 24%.
These insights highlight the estimator's relative strength in predicting the prices of used cars within a certain market segment, while also indicating areas where its accuracy may be less reliable.
<p><img src="https://github.com/RashmiTechie/BerkelyHaasCarEvaluation/tree/main/images/6_vs_kde_modified.png"></p>

## Interpreting Model Predictions and Understanding Limitations:

The predictions made by the model (represented as green dots in the visualization) that lie outside the outermost contour are likely outliers in the forecast and should be approached with caution.
Predictions that fall closer to or within the innermost contour tend to have a higher likelihood of aligning closely with actual sales prices. This spatial distribution in the visualization serves as an indicator of the confidence level in the model's predictions.
The presence of remaining data anomalies within the dataset is a key factor affecting the model's overall accuracy. The elimination of these anomalies would likely enhance the model's precision.
The model's percentage error rates are disproportionately influenced by lower-priced cars. This suggests that predictions in the lower price range should be interpreted with extra scrutiny.
The quality of the 'Actual' price data itself is questionable, necessitating a cautious approach when considering these values. Despite rigorous efforts in data cleansing, which led to the removal of many outliers, certain anomalies that do not fall into the extremes remain difficult to detect and eliminate.
The challenge in identifying and removing these subtler anomalies underscores the complexity of achieving a high level of data purity, which is crucial for the refinement and accuracy of predictive models.
<p><img src="https://github.com/RashmiTechie/BerkelyHaasCarEvaluation/tree/main/images/enhanced_6_actual_vs_predicted.png"></p>


A more sophisticated model incorporating 15 factors, including transmission type (manual or automatic) and car type (such as truck or sedan), was also tested. However, this model only achieved a modest improvement in the margin of error, reducing it by 2.6% compared to the simpler model.
This marginal enhancement in accuracy could signify inherent limitations in the chosen modeling approach. It suggests that the model, even with additional complexity, is only slightly more effective at capturing the nuances of car valuation.
The relatively small improvement with increased model complexity points to the need for a two-pronged approach for future enhancements:
Exploring More Advanced Models: There's potential for investigating other, possibly more sophisticated, modeling techniques that can better handle the complexity and nuances of used car pricing.
Improving Data Quality: Enhanced data quality is crucial for more accurate forecasting. Efforts should be directed towards further refining the dataset, removing anomalies, and possibly incorporating additional relevant factors that could impact car prices.
These steps are essential for achieving higher forecasting accuracy and for the model to effectively navigate the intricacies of the used car market.

## Consideration of Additional Influencing Factors:
 
While factors like car condition, title status, and specific features likely affect car prices, dataset anomalies and quality issues prevent their reliable use in predictions.

The inconsistencies necessitated the exclusion of certain variables like vehicle condition from the analysis.

Unmeasured elements like horsepower and the rarity of vintage cars also play a role in determining used car values but were not included due to data constraints.


