# Linear-Regression---King-County-Sales

## Author : Mercy Mukundi

## Business Understanding
According to Statista.com, in 2021, the U.S. home sales surged, reaching the highest value observed since 2006. A total of 6.1 million housing transactions were completed in that year, up from 5.6 million in 2020. The average house price also went up from 2020,  391,000𝑡𝑜  453,700 in 2021, with this trend expected to increase.

With this surge in housing transcations, as an analyst in Skyline Homes, a real estate company, I'm tasked with providing insights on how different factors affect house prices. The company sells their houses, but also helps connect house sellers to home buyers, ensuring both parties maximize on their investments.

Housing value estimation relies on technical pricing models whereby price is determined by both internal characteristics (bedrooms, bathrooms, living area, etc.) as well as external characteristics (neighboring houses, ZIP code, etc). With the great increase trend of the house price, a model with strong prediction power could help the company make the right decision on pricing their houses and those of their clients.

Creating such a model would greatly benefit Skyline, and its clients

## Objectives
- To build a model that predicts the price of houses with an acceptably high accuracy.

- To identify variables with the most weight when it comes to predicting the highest market price.

- To advice on the best investment strategy

## Data Understanding
The datset used for analysis contains house sale prices for King County in Washington, which includes Seattle. It includes homes sold between May 2014 and May 2015. The data was obtained from Kaggle. This data contains prices that the houses sold for, and also the featurs the houses had(18 columns). The data has 21,597 rows and 21 columns. The description of the columns is listed below, and the descriptive statistics are discussed in data wrangling.

#### Column Names and descriptions for Kings County Data Set
id - unique identified for a house
date - house was sold
price - is prediction target
bedrooms - of Bedrooms/House
bathrooms - of bathrooms/bedrooms
sqft_living - footage of the home
sqft_lot - footage of the lot
floors - floors (levels) in house
waterfront - House which has a view to a waterfront
view - Has been viewed
condition - How good the condition is ( Overall )
grade - overall grade given to the housing unit, based on King County grading system
sqft_above - square footage of house apart from basement
sqft_basement - square footage of the basement
yr_built - Built Year
yr_renovated - Year when house was renovated
zipcode - zip
lat - Latitude coordinate
long - Longitude coordinate
sqft_living15 - The square footage of interior housing living space for the nearest 15 neighbors
sqft_lot15 - The square footage of the land lots of the nearest 15 neighbors

## Methodology
![Data-Science-OSEMN-1](https://user-images.githubusercontent.com/58382818/177064270-839bfacf-27c9-4400-981e-cb115bc3b868.png)

### 1. Obtain
The data was downloaded from Kaggle, and loaded into the jupyter notebook using pandas. 

### 2. Scrub

The data was checked for null values, and the null values dealt with. Since the dataset was small, imputation is done to fill in the null values.
The data was also checked for duplicates, and the duplicates dropped.
The data types of the variables are adjusted to replect the true variable data types.
Outliers were also removed from the dataset. The z-score method was used, where z scores of the variables, higher than 3 was regarded as an outlier and dropped.
Some of the data was converted to other variables, eg, the column yr_renovated was converted to the column renovated, that hosts binary values of whether a house has been renovated or not.

### 3. Explore

Exploratory Data Analysis(EDA) was done. 
Univariate, bivariate and multivariate analysis was done.

### 4. Model

Modelling was done using both Statsmodels and sklearn linear regression models.
Models were created iteratively until the final model was gotten with the best variables.
Model validation was done to ensure the model was accurate.
Linear regression assumptions were tested

### 5. Interpret

The coefficients and intercept of the model were interpreted on how they affect the price of the houses.
Conclusions and recommendations were made on the results of th model.

## Results

The model was able to explain 78% of bthe variances in the data. The variables with the highest effect of price were :
- Location
- Living area space
- Condition of the house
- Age of the house

## Conclusions

- The size of the living space was deemed to be crucial in determining house price. It got a ranking of 1 during feature selection, meaning i is an important variable. It has a coefficient of 304,955. This means that an increase in 1 square foot of the living space, causes an increase in price by 304,955 dollars.

- Location is also a major factor affecting price. From the zipcodes with the highest coefficients, the top 5 zipcode coefficients belong to the following cities:

  - Medina (859,833)
  - Bellevue (660,258)
  - Seattle (620,984 and 556,407)
  - Mercer Island (560,801)
  
These cities border Lake Washington, meaning some of the properties have a waterfront view. This can explain the drastic difference in prices in such cities. Medina had the highest coefficient of all the variables. It has a coefficient of 859,833. This means that choosing to buy a house there could cost upwards of 859,833 dollars. Same effect as the other cities and their coefficients

- The condition of the house also has an effect on the price. Houses with a condition of 5, meaning they are in very good condition cause an increase in the price by 159,840 dollars. Condition 4, closely follows with an effect of 126,182 dollars. Condition 4 houses are good. Houses in average condition, condition 3, cause an increase by 111,256 dollars. There is a huge difference between the effect price of condition 5 and 3, further cementing that a high condition number of the house will cause a relatively substantial increase in the price. Houses of condition 1 and 2, which are poor, have a low effect on the price.

- Bedrooms have a negative coefficient on the price. Meaning an increase in the number of bedrooms causes a decrease in the price. Hence, it is advisable that that Skyline home should focus on houses with a low mumber of bedrooms, 1, 2 or 3. They should also advice their clients the same.

- The age of the houses also has an effect on the price. Newer homes, below 20 years have a larger effect on the price, compared to older homes, hence Skyline should venture into selling newly constructed houses. The same goes for their clients.

## Recommendations

Further analysis could be done on the demographic of Kings County. Also, analysis into the purchasing power of the people of King County could give an insight into whether there are alot of people who can spend their money on buying high priced houses, or not. Knowing this information would give Skyline homes insights on whether they should be selling high priced houses, or sell cheap houses. 



