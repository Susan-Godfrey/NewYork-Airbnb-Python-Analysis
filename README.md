# NewYork Airbnb Market Analysis

### Introduction
De-Stingray, A real-estate startup has been into residential rentals and are looking to invest into short-term rentals. They need a detailed market analysis on New York Airbnb listings.

### Data Source
The dataset was gotten from Kaggle, with a description of it being scraped from Inside Airbnb website.

### Objectives
- What room type listings are in demand for each borough?
- What is the average price distribution of listings for each borough?
- Is there a major effect of license on price listings?
- What is the percentage of listings with license compared to listings without license?
- What is the property trend for bedrooms and baths?
- What is the average price distribution of room type?
- Identify the number of active listings through guest engagement or reviews.
- Are there more professional short-term rentals listed?
- Based on the price, are professional short-term listings higher?
- Is there a relationship between price & bedrooms and price & availability?

### Summary Chart of Workflow Process before Analysis and Viz
#### *Before Data Cleaning*
Total Records  --  20758  
Number of Columns – 22  
Number of Duplicates  --  No duplicates found  
There are no missing values in all columns and rows  
Numeric columns – 12  
Qualitative columns – 10

|Columns|Description|EDA|Data Cleaning & Transformation|
|-------|-----------|---|------------------------------|
|Id|Unique ID’s of each rows in the data|20,758 unique values of a numeric column.|No Issues.|
|name|Brief description of the listing, specifying its features as well.|9,836 unique values of a qualitative column.|Replaced unwanted string characters with nothing. |
|host_id|Unique ID’s of host having listings on Airbnb.|12,449 unique values of a numeric column.|No Issues.|
|host_name|Name of hosts.|5,815 unique values of a qualitative column.|No Issues.|
|neighbourhood_group|Different areas/borough in New York. |5, unique values of a qualitative column.|Renamed column header to ‘borough’.|
|neighbourhood|Neighbourhood city around each borough.|221 unique values of a qualitative column.|No Issues.|
|latitude|Latitude of New York based on each listings address.|15,382 unique values of a numeric column.|No Issues.|
|longitude|Longitude of New York based on each listings address.|14,477 unique values of a numeric column.|No Issues.|
|room_type|The type of room listed.|4 unique values of a qualitative column.|No Issues.|
|price|Price of listing.|785 unique values of a numeric column.|No Issues.|
|minimum_nights|The least number of nights a listing can be booked.|69 unique values of a numeric column.|Major outliers found.|
|number_of_reviews|Count of reviews.|470 unique values of a numeric column.|No Issues.|
|last_review|Last date a listing got reviews.|1878 unique values of a qualitative column.|Renamed column header to ‘last_review_date’. Changed data type to Datetime. Extracted the year to create a new column called ‘last_review_year’.|
|reviews_per_month|Average reviews per month.|783 unique values of a numeric column.|No Issues.|
|Calculated_host_listings_count|Number of listings a host has.|68 unique values of a numeric column.|Renamed column header to ‘number_of_host_listings’.|
|availability_365|The number of days a listing is available/open to be booked within a year.|366 unique values of a numeric column.|No Issues|
|number_of_reviews_ltm|Number of reviews last month.|153 unique values of a numeric column.|No Issues.|
|license|Listings with license and those without license.|879 unique values of a qualitative column.|Standardize the values starting with ‘ose-strrng’. Extract OSE values to create a new column called ‘license_category’.|
|rating|Ratings of each listings.|162 unique values of a qualitative column.|Replaced ‘No rating ’ and ‘New’ values to 0. Changed datatype to float.|
|bedrooms|Number of bedrooms in a listing.|12 unique values of a qualitative column.|Replaced ‘Studio ’ values with 0. Changed datatype to integer.|
|beds|Number of beds in a listing.|17 unique values of a numeric column.|No Issues.|
|baths|Number of baths in a listing.|17 unique values of a qualitative column.|Replaced ‘Not Specified’ with 0. Changed datatype to integer.|

#### *After Data Cleaning & Transformation*
Total Records  --  20758  
Number of Columns – 26  
Datetime columns – 1  
Numeric columns – 16  
Qualitative columns – 9  
Created 4 new columns, such as: other_listings, host_listing_status, license_category & last_review_year

### Analysis
#### KPI's
![KPI's](https://github.com/user-attachments/assets/a82d2068-dee7-48fe-98c5-a392af291cb6)

- **Room Type Listings for each Borough:**  
Different room types are more common in certain areas of New York compared to other areas. In Brooklyn, Manhattan, & Staten Island, Entire home/apt is in demand with 4129, 5288 and 156 listings. While in Bronx & Queens, Private room with 544 and 2093 listings is the most common room type guest opt for. This is the pattern for the different areas in New York.  
![Listings by Borough](https://github.com/user-attachments/assets/8ad6b6cb-7604-4867-b366-8ddee3f7674d)

- **Average Price Distribution of Listings for each Borough:**  
Manhattan has the highest average price of listings made in New York with an amount of $227,  compared to other boroughs which are less than $190.  
![Avg Price by Borough](https://github.com/user-attachments/assets/eb148af0-c932-4748-9230-234d7c15c355)

- **Effect of License on Price Listings:**  
Based on the average price across each license category, specifying those with the OSE license and those without license, we can see from our chart that those proclaimed Exempted of the use of license has higher average price listings with about $274. While there’s not much difference between those without license (No License) and those with license (OSE License). This shows that the possession of OSE License does not have any effect of listings price.  
![Avg price by License](https://github.com/user-attachments/assets/950089c6-fdee-4255-89f1-17f8b8a0f2f9)

- **Percentage of Listings with License & No License:**  
The data shows that 84.6% of listings on Airbnb in New York have No License.  
![% of Listings by License](https://github.com/user-attachments/assets/22d9b081-d5ee-40d6-94a7-fd671de2c93d)

- **Property Feature Trend:**  
The average number of bedrooms, baths and beds in New York is 1 each for rooms listed in Airbnb.  
![Avg Bedrroms and Baths](https://github.com/user-attachments/assets/fba13ae9-0b5b-4dab-8d73-573241bd0cdd)

- **Average Price Distribution of Room Type:**  
Based on the distribution of room types listed, Hotel rooms have a higher average price of $415, while Entire home/apt is the second highest with an amount of $223.  
![Avg Price by Room Type](https://github.com/user-attachments/assets/ce1104b7-371a-48c0-991d-b4b53f4a96bd)

- **Number of Active Listings by Guest Reviews:**  
Based on the reviews of guests since 2011 to 2024, there has been an increase in trend with an  estimate of 9553 active host in 2023. After which there was a significant drop of hosts in 2024 which was likely due to the initiation of Local Law 18 that took effect in September 2023 on short-term rentals. 2023 therefore, experienced the most active listings from guests.  
![Active Listings Trend](https://github.com/user-attachments/assets/2b5bcc07-14d6-4db1-ae7b-934d1f7e86af)

- **Host Status on Short-term Rentals:**  
Across all listings in New York, the most common listings are placed by Professional hosts with a total number of 10,973 listings; who are available within 181 -365 days. The second highest listings are made by Seasonal hosts that has an amount of 6557 listings.  
![Listings by Host status](https://github.com/user-attachments/assets/91b00572-adc5-44e7-9548-b8ff12874f03)

- **Average Price by Host Status:**  
Professional hosts have a higher average price of $203. While Occasional hosts with listings less that 30 days ranks second with an average price of $177.  
![Avg Price by Host status](https://github.com/user-attachments/assets/34f09cd3-9a09-4d1f-ac7e-3161ad15cd84)

- **Correlation between Price & Bedrooms, and Price & Availability:**  
The data shows a correlation of 0.069 score between Price & Bedrooms, meaning that there’s no relationship between Price & Bedrooms. Therefore, the number of Bedrooms does not determine the Price of a listing. Also, the same result is interpreted for Price & Availability that shows a correlation score of 0.02.  
![Correlation matrix](https://github.com/user-attachments/assets/ae7f1ea9-9e55-4c1f-bfa7-685c95333edb)

### Recommendations
- Based on the analysis, I recommend that De-Stingray invest in boroughs like Manhattan and Brooklyn which not only have higher Price range, but also have more demands on rooms like Entire home/apt and Private room. While also considering Queens Borough for potential investment.
- With the research carried out on Local Law 18 and with the fact extracted from our analysis on the percentage of listings with license, as well as the average price of listings based on license; De-Stingray can set up a short-term rental without license as long as the minimum nights for each listing is 30 & above.
- Given that Professional host have higher returns, De-Stingray can look into providing listings that are available for at least 180 to 365 days.
- Seeing that there’s no relationship between bedrooms and price, or availability and price; it shows that the feature of a listing does not determine the spike of price. Therefore, I recommend that De-Stingray look into more tourist attraction places aside from Manhattan and Brooklyn seeing that location has a major impact on price and demand of listings.























