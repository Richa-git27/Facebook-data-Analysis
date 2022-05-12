##  Data Description

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
Numpy : for background calculations
Pandas : for data manipulation
Matplotlib : for data visualization
Seaborn : for advanced data visualization
