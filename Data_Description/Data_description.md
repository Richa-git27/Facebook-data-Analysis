#  Data Acquisition & Description

This dataset is taken from already existing databases from Facebook Inc Datacenter

The Dataset contains unique UserIDs of Facebook users, their age, date of birth, gender, tenure of using facebook, their Friend count, friendships they initiated, number of likes given and received and number of likes given and received through mobile and web application respectively.

|Id|Feature|Description|
|:--|:--|:--|
|01| userid                 | A numeric value uniquely identifying the user.|
|02| age                    | Age of the user in years.|
|03| dob_day                | Day part of the user's date of birth.|
|04| dob_year               | Year part of the user's date of birth.| 
|05| dob_month              | Month part of the user's date of birth.|
|06| gender                 | Gender of the user.| 
|07| tenure                 | Number of days since the user has been on FB.|
|08| friend_count           | Number of friends the user has.|
|09| friendships_initiated  | Number of friendships initiated by the user.|
|10| likes                  | Total number of posts liked by the user.|
|11| likes_received         | Total Number of likes received by user's posts.|
|12| mobile_likes           | Number of posts liked by the user through mobile app.|
|13| mobile_likes_received  | Number of likes received by user through mobile app.|
|14| www_likes              | Number of posts liked by the user through web.|
|15| www_likes_received     | Number of likes received by user  through web.| 

## Importing Libraries

I used basic libraries for EDA on this dataset such as:
- Numpy : for background calculations [![](https://raw.githubusercontent.com/Richa-git27/Facebook-data-Analysis/main/Data_Description/NUmpy.jpg)](https://raw.githubusercontent.com/Richa-git27/Facebook-data-Analysis/main/Data_Description/NUmpy.jpg)
- Pandas : for data manipulation [![](https://raw.githubusercontent.com/Richa-git27/Facebook-data-Analysis/main/Data_Description/pandas.png)](https://raw.githubusercontent.com/Richa-git27/Facebook-data-Analysis/main/Data_Description/pandas.png)
- Matplotlib : pyplot interface for data visualization [![](https://raw.githubusercontent.com/Richa-git27/Facebook-data-Analysis/main/Data_Description/mplt.png)](https://raw.githubusercontent.com/Richa-git27/Facebook-data-Analysis/main/Data_Description/mplt.png)
- Seaborn : for advanced data visualization [![](https://raw.githubusercontent.com/Richa-git27/Facebook-data-Analysis/main/Data_Description/seaborn1.png)](https://raw.githubusercontent.com/Richa-git27/Facebook-data-Analysis/main/Data_Description/seaborn1.png)
```python
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns
```

------------

After checking the shape of data and performing the describe function on the dataset following are the observations:

- There are 14 continuous features in the data for which we obtained description

- UserID feature is an identifier so we won't be making any statistical observation for it.

- The minimum and maximum ages of people using Facebook are found to be 13 and 113 while the average age using Facebook is found to be 37 years.

- Around 50% of people(median) have an age less than or equal to 28 years which is 9 years less than the average age(mean) which shows that there is positive skewness in age distribution.

- Since Date of birth features are segregated and are in integer type, we have to explore them more.

- The average tenure of people using Facebook is found to be 538 days whereas the maximum tenure is 3139 days.

- The minimum and maximum friend count are found to be 0 and 4923 while the average friend count is found to be 196.

- Around 50% of people(median) have a friend count less than or equal to 82 which is much less than the average friend count(mean) which shows that there is positive skewness in friend count distribution too.

- Around 50% of people have less than or equal to 46 friendships initiated whereas the maximum friendship initiated are 4144.

- The posts liked by 50% people are 11, average likes are 156 whereas maximum likes are as high as 25111.

- The likes received on posts by 50% people are 8, average likes received are 143 whereas maximum likes received are as high as 261197.

- The post liked by 50% people on mobile app are 4, average mobile likes are 106 whereas maximum mobile likes are 25111

- The likes received on mobile app by 50% people are 4, average mobile likes received are 84 whereas maximum mobile likes received are 138561.

- The post liked by 50% people on web app 0, average web likes are 50 whereas maximum web likes are as high as 14865.

- The web likes received on posts by 50% people are 2, average web likes received are 58 whereas maximum web likes received are as high as 129953.

- Since the median is less than mean in almost all the categories it implies that the data is most likely to be positively skewed.

## Data Information

- The dataset has 99003 rows and 14 columns

- Tenure is of float64 datatype and rest 13 features are all int64 datatype.

- The date of birth is segregated into dob_day, dob_year, dob_month making it int64 datatype.

- From the glimpse of information we can find out that there are some missing observations in gender and tenure features and we will explore more about it.
