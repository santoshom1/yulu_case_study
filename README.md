## TABLE OF CONTENT:
- [ABOUT YULU & DATASET](#yulu-case-study)
- [UNIVARIATE ANALYSIS](#univariate-analysis)
- [BI-VARIATE ANALYSIS](#bi-variate-analysis)
- 


## yulu case study
Yulu is India’s leading micro-mobility service provider, which offers unique vehicles for the daily commute. Starting off as a mission to eliminate traffic congestion in India, Yulu provides the safest commute solution through a user-friendly mobile app to enable shared, solo and sustainable commuting.
Yulu zones are located at all the appropriate locations (including metro stations, bus stands, office spaces, residential areas, corporate offices, etc) to make those first and last miles smooth, affordable, and convenient. 
Yulu has recently suffered considerable dips in its revenues. They have contracted a consulting company to understand the factors on which the demand for these shared electric cycles depends. Specifically, they want to understand the factors affecting the demand for these shared electric cycles in the Indian market.
## the company wants to know
- Which variables are significant in predicting the demand for shared electric cycles in the Indian market?
- How well those variables describe the electric cycle demands
## dataset - [link](https://d2beiqkhq929f0.cloudfront.net/public_assets/assets/000/001/428/original/bike_sharing.csv?1642089089)

- Click here to view the full case study notebook:
📘 [View Notebook](Yulu.ipynb)
- Open it directly in Colab:  [▶️ Open in Colab (right-click to open in new tab)](https://colab.research.google.com/drive/1W0CqPQukjjhwfaMl6nTZaYWC-KL49mPC)

## Basic Exploration
- There are 10886 rows of data for each column
- Here columns seems to be having one object type variable and rest other are numeric variables
- The data has No missing values or null values or any duplicated values
- Datetime columns holds unique values for every row, season and weather has on 4 unique categories followed by holiday and workingday columns having 2 unique categories.

- For these columns it is better for our understanding to assign unique names for unique categories in each column as given in the problem statement .Now we have 5 object type columns, and 7 numerical and 1 date time column in the data.

## UNIVARIATE ANALYSIS
**Temperature(temp)** :  The temperature data is roughly normally distributed , indicating moderate temperature  are the most common

**Humidity**  : Humidity data is also similar to normal distribution with a peak around 60-80%, Indicating moderate to high humidity is common.

**Windspeed** :  Windspeed data is heavily skewed towards lower values indicating most days have lower wind speeds

**Casual** : The distribution is heavily right skewed with most days having  a low number of casual users  but a very few days showing high usage

**Registered** : Similar to casual users the distribution is right skewed  though the count of registered users generally higher than casual users 

**Total Rentals** :  The distribution is right-skewed, with most days having a low total count of rentals, but a significant number of days having high rental counts

![image_alt](https://github.com/santoshom1/yulu_case_study/blob/e8ea4124ea1085a408bf0dbdb15838db248560c2/Uni-variate.png)

## BI-VARIATE ANALYSIS:
**working day & holiday analysis:**
- There were Only 2.8 percent of Holiday records out of 10 thousand records where non-working days holds 32% of records, this difference is because of which weekends were not included in holidays.
- Working day holds 68 % of the data whereas non-holiday holds 97% of the records
![image_alt](https://github.com/santoshom1/yulu_case_study/blob/cd9ff810e3a7ecaedf6ea8f0bff682105b5dff21/work-nonwork.png)

**season and workingday:**
- Three seasons summer, winter and fall are mostly having same value holding 2730 records each However fall is having Most number of bike rentals followed by summer and winter. where as spring shows a high dip on the bike rentals.

![image_alt](https://github.com/santoshom1/yulu_case_study/blob/109e5352637bbeb28a89470e833908e060b3b58f/Screenshot%202025-07-17%20190230.png)
- from the below barplot it is observed that working has no effect on the bike rentals season wise. For any season whether it might be a working day or not the impact on the bike rentals looks significantly similar.

![image_alt](https://github.com/santoshom1/yulu_case_study/blob/109e5352637bbeb28a89470e833908e060b3b58f/seasonal.png)

**season and weather:**
- Most of the data contains the record of the weather condition as clear or cloudy and most of the rentals were made in this weather condition only as it is suitable for anyone to ride in this condition.
- The second most is misty and cloudy weather where it holds 5 lakh number of bike rentals closely to 30 % of the total rentals
- Heavy rain and snowy weather shows the least number of bike rentals, as weather is not suitable for anyone to be outside the roof.
- the below bar plot tells us spring being the least contributor to the total bike rentals across all weather conditions.
  where as the rest of three seasons shows significantly contributing equally to the total rentals across all the seasons.
![image_alt](https://github.com/santoshom1/yulu_case_study/blob/1cc0cbc578665a74a69cd2955ee1af5c71d35cdf/season%2Bweather.png)

**temperature vs totalrentals:**
- Bike rentals were mostly rented in between the temperature of 15 to 35 celcius , indicating moderate temperature are the most common

![image_alt](https://github.com/santoshom1/yulu_case_study/blob/f7937365c946230cd6729af081cd9bb5b06dd769/temp.png)

- The temperature people likely to rent a bike and travel is around the temperature between 25 to 30 celcius as shown in the picture below
![image_alt](https://github.com/santoshom1/yulu_case_study/blob/d70893b836f94f11574a9c87ab823e31528267dc/ws%20vs%20total%202.png)

**Humidity vs Total_rentals:**
- The Humidity in which people likely to rent a bike and travel is between 40 to 60 as shown in the picture below
![image_alt](https://github.com/santoshom1/yulu_case_study/blob/d70893b836f94f11574a9c87ab823e31528267dc/ws%20vs%20total%201.png)

**windspeed vs Total_rentals:**
- The Windspeed where people likely to rent a bike and travel is around the windspeed between 0 to 20  as shown in the picture below, more the windspeed less people are likely to rent a bike,
- 
![image_alt](https://github.com/santoshom1/yulu_case_study/blob/a75b9166a9b4e846fdf1b90860ff56624d2f55a8/humidity%20vs%20total.png)
![image_alt](https://github.com/santoshom1/yulu_case_study/blob/d70893b836f94f11574a9c87ab823e31528267dc/temp%20vs%20total.png)


***Business Objective 1:***

**- Which variables are significant in predicting the demand for shared electric cycles in the indian market?**

***Strategic Objective:***

- for this to be answered there are some variables that needs to be tested with count of bike_rentals to check for dependency.
- 
**Weather vs Total_rentals:**
  
- H0 : There is no significant difference in bicycle demand across different weather conditions.
- H1 : There is a significant difference in bicycle demand across different weather conditions.
*weather where heavy rain or snow occurs has no significance to the demand as it has fewer records.*
- the qqplot we got shows us that data is not normally distributed and for levene's test also shows us variances are not equal which brings us to non-parametric tests.
- kruskal test is one of the non-parametric test which is replacement of ANOVA when anova assumptions are not met. After doing kruskal-vallis test p-value obtained is signifcantly lower than any aplha value then null hypothesis is rejected.
- Here; pval = 3.12206618e-45, Consider an alpha as 0.05. since pval is very much lesser than alpha Null Hypothesis is Rejected and We can conclude that ***There is a significant difference in bicycle demand across different weather conditions.***
- 
**Season vs Total-rentals:**
  
**H0 : Season has no effect on bike rentals**

**H1 : Season has effect on bike rentals**
- Three seasons summer, winter and fall are mostly having same value holding 2730 records each However fall is having Most number of bike rentals followed by summer and winter. where as spring shows a high dip on the bike rentals.
- the qqplot we got shows us that data is not normally distributed and for levene's test also shows us variances are not equal which brings us to non-parametric tests.
- kruskal test is one of the non-parametric test which is replacement of ANOVA when anova assumptions are not met. After doing kruskal-vallis test p-value obtained is signifcantly lower than any aplha value hen null hypothesis is rejected.
- Here Pval : 2.2263613e-151, Consider an alpha as 0.05. since pval is very much lesser than alpha Null Hypothesis is Rejected and We can conclude that ***Season has effect on bike rentals.***
***As per the numbers working day and holiday columns any way have power over demand for bike rentals.***

***Business Objective 2:***

**- Working day has effect on number of electric cycles rented?**

***Strategic Objective:***

**H0 : Working day has no effect on bike rentals**

**H1 : Working day has effect on bike rentals**
- A non working day has over 6.5lakh bike rental records where as a working day holds records 14.5 lakh bike rentals which suggests that bikes are mostly rented by employees on their way to office from home or home from office
- the qqplot we got shows us that data is not normally distributed and for levene's test also shows us variances are not equal which brings us to non-parametric tests.
- kruskal test is one of the non-parametric test which is replacement of ANOVA when anova assumptions are not met. After doing kruskal-vallis test p-value obtained is signifcantly lower than any aplha value hen null hypothesis is rejected.
- Here Pval :0.9667, Consider an alpha as 0.05. since pval is very much higher than alpha we fail to reject Null Hypothesis and We can conclude that ***working day has no effect on bike rentals.***

***Business Objective 3:***

**- No.of  Cycles rented similar or diffrent in diffrent seasons?**

***Strategic Objective:***

- Number of cycles rented are different in different seasons

![image_alt](https://github.com/santoshom1/yulu_case_study/blob/9b6ee19dbaa862ad4635260b48027485ad447ec3/Screenshot%202025-07-24%20150842.png)

***Business Objective 4:***

**- No.of Cycles rented similar or different in different weather?**

***Strategic Objective:***
- yes, number of cycles rented rented are diffrent in different weather 
![image_alt](https://github.com/santoshom1/yulu_case_study/blob/9b6ee19dbaa862ad4635260b48027485ad447ec3/Screenshot%202025-07-24%20150912.png)

- ***From the above Data it is clearly observed that people are mostly like to prefer clear or cloudy weather to rent a bicycle.***

**CORRELATION BETWEEN FEATURES:**
<img width="1920" height="1080" alt="Screenshot (3680)" src="https://github.com/user-attachments/assets/584fbc89-a2db-4e52-b6ce-c8ce2940d83d" />

**High positive Correlation:** 

- Registered And Total_rentals: 
The number of registered users is highly positively correlated with the total count of rentals at 0.97, implying that registered users significantly contribute to the overall count.
- Casual Ans Total_rentals: 
The number of Casual users is highly positively correlated with the total count of rentals at 0.69, implying that Casual users are considerable part of the total users base.

**Moderate positive Correlation:**
- temp and total rentals: Temp and total rentals are correlated at a value of 0.39, this suggests that higher temperatures are associted with an increased demand for bicycles.

**Negative Correlation:**

- Humidity and  total rentals: 
Humidity and count are correlated at a value of -0.32, Higher humidity values are moderately negatively correlated with the total rentals  indicating that people are less likely to rent bicycles in more humid conditions.

- windspeed and casual : 
windspeed negatively correlates with the count of casual users at -0.32, suggesting that higher windspeeds may prevent the occurances of casual users.

**Observation:**

- weather and humidity(0.41) : weather conditions show a moderate positive correlation with humidity, indicating that certain weather conditions are associated with higher humidity levels.

***BUSINESS INSIGHTS:***

-**Temperature influence:**
Higher temperatures are associate with the increased bicycle rentals. 

**Strategic Implication:**
Enhance service availability and marketing efforts During warmer periods to capture higher demands.

**Humidity and Windspeed:**
Higher humidity and windspeed negatively affect bicycle rentals. Humidity shows a negative correlation(-0.32) with total rentals while wind speed negatively correlates (-0.32) with casual users.

**Strategic Implication:**
Provide incentives or promotions during high humidity or wind speed periods to maintain rental numbers.

**Weather Conditions:**
weather condition significantly affect bicycle demand. Clear weather pulls the highest demand, while adverse weather condition reduce rentals.

**Strategic Implication:**
Monitor weather forecasts and adjust operations accordingly, possibly offering discounts or special services during less favorable weather.

**Seasonal variations:**
Bicycle demand varies significantly across seasons, with specific seasons showing higher total rentals.

**Strategic Implication:**
Plan inventory and staffing based on seasonal demand trends to optimize operations and costs.

**Registered vs Casual Users:**
Registered users have a high positive correlation (0.97) with the total count, indicating they are the primary drivers of demand while casual users also significantly contribute to the total count(0.69)

**Strategic Implication:**
Focusing on expanding the registered user base through loyalty programs and target marketing.

**Weekday vs Weekend Demand:**
There is no significant difference in the number of bike rides between weekdays and weekends.

**Strategic Implication:**
Maintain consistent service levels throughout the week, without needing drastic operational changes between weekdays and weekends.

**Impact of Holidays:**
Holidays account for a small propotion of the data but can show spikes in the demand.

**Strategic Implication:**
prepare for potential demand spikes on holidays with promotional events or increased inventory.

**CONCLUSION:**

*By leveraging these insights, Yulu can enhance their operational efficiency , optimize inventory management, and develop targeted marketing strategies. Understanding the impact of various factors on bicycle demand enables data-driven decision making, leading to improved customer satisfaction and increased profitability.*
