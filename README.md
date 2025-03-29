# Restaurant Rating Analysis

![Restaurant Rating Introduction](Restaurant-Rating-Introduction.jpg)

## Introduction
This is a Power BI project on Restaurant Rating Dataset which contains information about restaurants in Mexico. A customer survey was carried out in this city in 2012 to collate information about each restaurant, their cuisines, information about their consumers and the preferences of the consumers. The objective of this project to analyze and draw out meaningful insight from this dataset which would aid business entrepreneurs and investors in making more informed decisions. 

**_Disclaimer_**: _All datasets and reports do not represent any company, institution, or country. It is just a dummy datatset used to demonstrate the capabilities of Power BI._

## Problem Statement

1. What can you learn from the highest rated restaurants? Do consumer preferences have an effect on 
ratings?
2. What are the consumer demographics? Does this indicate a bias in the data sample?
3. Are there any demand & supply gaps that you can exploit in the market?
4. If you were to invest in a restaurant, which characteristics would you be looking for? 

 ## Skills/Concepts Demonstrated 
 
The following Power BI features where incorporated:
- Power Query (Data cleaning and transformation),
- Data Modeling,
- DAX,
- Data Presentation (Visualizations),
- Filters and Interactivity

  ## Data Sourcing

  The dataset used for this analysis was sourced from Restaurant Rating Dataset. The data consists of the following tables:
  - Consumers
  - Consumer Preferences
  - Ratings
  - Restaurants
  - Restaurant Cuisines

  ## Data Transformation
  Before analysis, the dataset underwent data cleaning and transformation in power query.
  Key steps include:
  - Removing duplicates,
  - Handling missing values,
  - Standardizing data types,
  - Grouping the Age column using bins.
 
  ## Data Modeling

  ![Restaurant Rating Model](Restaurant-Rating-Model.PNG)
  
  The Restaurant Rating data model was structured using a star schema approach, with the ratings table as the central fact table, consumers and restaurants tables as the two dimensions table. Both were joined to the fact table with a one-to-many relationship.

  ## DAX Measures

  The following DAX measures were used to calculate key metrics within the dataset:
  - Avg_Restaurant_Ratings = AVERAGE(ratings[Overall_Rating])
  - Consumer_Demand = CALCULATE(COUNT(consumers[Consumer_ID]),ALLEXCEPT(consumer_preferences, consumer_preferences[Preferred_Cuisine]))
  - Demand_Supply_Gap = consumers[Consumer_Demand]-restaurants[Restaurant_Supply]
  - Restaurant_Supply = DISTINCTCOUNT(restaurant_cuisines[Restaurant_ID])

  ##### This project documentation contains screenshots of data visualization as a means to interpret and easily read results gotten from my analysis.

  ## Data Analysis and visualization

  ![Restaurant Rating Dashboard](Restaurant-Rating-Dashboard.PNG)

  - #### What can you learn from the highest rated restaurants? Do consumer preferences have an effect on ratings?
    Three restaurants achieved the highest rating of 2.0;
    1. Emilianos
    2. Michiko Restaurant Japones
    3. Restaurant Las Mananitas
    
    However, consumer preferences do not have an effect on these ratings as most consumers prefer mexican cuisine while these restaurants offer brewery, japanese and international cuisine.

  - #### What are the consumer demographics? Does this indicate a bias in the data sample?
    
    ![Customer demography by cuisine](Customer-demography-by-cuisine.PNG)
    
    From the dashboard, the key consumer demographics are:
    - Preferred Cuisine: Mostly Mexican, American and Pizzeria.
    - Age Group: Majority of the consumers are within the 18-35 age group
    - Occupation: Mostly Students
    - Budget: Mostly Meduim and Low-budget consumers
    - Marital status: 92.75% single, 7.25% married
    - City Distribution: 62.32% from San Luis Potosi, 18.12% from Ciudad, 15.94% from Cuernavaca and 3.62% from Jiutepec.
    
    This indicates a bias within the data sample as the dataset is not evenly distributed across multiple cities, underrepresents married consumers and high budget diners. Also, the dataset likely skews towards younger consumers potentially underrepresenting older demographics who may have different dining preferences.

  - #### Are there any demand & supply gaps that you can exploit in the market?

    ![Demand-Supply Gap](Demand-Supply-Gap.PNG)

    Key findings from the dashboard:
    - Consumer demand for Mexican cuisine is very high. However, the restaurant supply for Mexican cuisine is also high. There is a -25 demand-supply gap, which indicates that the market is nearly balanced, hence no major gap exists. Investing in another Mexican restaurant may not be profitable unless it has a unique selling point.
    - Consumer demand for other cuisines (American, Pizzeria, Family, Chinese) is also high but the restaurant supply is low. There is a -100+ demand-supply gap, whhich indicates  high potential investments.
    - There is low demand for other cuisines, hence the restaurant supply vary. Investing in these cuisines may not be profitable due to low demand.

  - #### If you were to invest in a restaurant, which characteristics would you be looking for?
    
    ![Restaurant By Overall Rating](Restaurant-By-Overall-Rating.PNG)

    Based on the Demand-Supply gap analysis, Consumer preferences and Restaurant ratings, the ideal restaurant for investment should have the following characteristics:
    - Restaurants offering American, Pizzeria, Family and Chinese Cuisines. These cuisines have high demand but low restaurant supply.
    - Restaurants in cities where demand is high but few restaurants exist. San Luis Potosi is oversaturated, other cities should be considered.
    - Restaurants that can offer budget friendly options. Since most of the consumers are young and budget conscious, a mid range pricing restaurant will attract both budget conscious and quality seeking customers.
    - Restaurants under franchise as they pose lower risk for investments.
   
  ## Conclusion
  This analysis highlights key market opportunities in the restaurant industry in mexico. To maximize success in investments, investors should focus on underserved cuisines, choose the right locations,and prioritize customer experience.
