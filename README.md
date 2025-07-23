# yulu_case_study
Yulu is India’s leading micro-mobility service provider, which offers unique vehicles for the daily commute. Starting off as a mission to eliminate traffic congestion in India, Yulu provides the safest commute solution through a user-friendly mobile app to enable shared, solo and sustainable commuting.
Yulu zones are located at all the appropriate locations (including metro stations, bus stands, office spaces, residential areas, corporate offices, etc) to make those first and last miles smooth, affordable, and convenient. 
Yulu has recently suffered considerable dips in its revenues. They have contracted a consulting company to understand the factors on which the demand for these shared electric cycles depends. Specifically, they want to understand the factors affecting the demand for these shared electric cycles in the Indian market.
# the company wants to know
- Which variables are significant in predicting the demand for shared electric cycles in the Indian market?
- How well those variables describe the electric cycle demands
# dataset - [link](https://d2beiqkhq929f0.cloudfront.net/public_assets/assets/000/001/428/original/bike_sharing.csv?1642089089)

- Click here to view the full case study notebook:
📘 [View Notebook](Yulu.ipynb)
- Open it directly in Colab:  [▶️ Open in Colab (right-click to open in new tab)](https://colab.research.google.com/drive/1W0CqPQukjjhwfaMl6nTZaYWC-KL49mPC)

# Basic Exploration
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
