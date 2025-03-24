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








