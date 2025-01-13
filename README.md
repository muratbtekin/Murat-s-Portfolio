# Murat-s-Portfolio

## What was asked?

Director of the marketing believes that the company's success depend on converting casual users to annual members. Hence she asks me (I am a junior data analyst) to provide insights through data visualizations in order to convince the executive team.

The details are to be found here: https://artscience.ai/divvy-dataviz-case-study/

### Gathering the Data

In this project I first downloaded the datasets from here https://www.kaggle.com/datasets/bchen02/google-data-analytics-certificate-bike-share](https://divvy-tripdata.s3.amazonaws.com/index.html

I selected the datasets from August 2020 all the way up to July 2021 so that I could view the change in users' behaviour depeding on seasons.

### Combining the Data

I first used Colab, utilizing python to join 12 datasets.

https://colab.research.google.com/drive/1wMdDetjCncKObr7QE2oWTZHytHOvWNW6?usp=sharing

### Preparing the Data

Then I changed the data type of started_at and ended_at from object to datetime and subtracted started_at from ended_at to derive the 'duration' column.

Thereafter I dropped the rows where the duration is less than 0.

The rows where 'start_station_name', 'start_station_id', 'end_station_name', 'end_station_id' values were empty, were also dropped to have a more robust dataset.

After the aforementioned steps, I moved on with Dataiku to further process the data, yet I resorted to using Python again when I felt the need to do so.

Using Dataiku's preparation steps, I derived the 'Weekend' column, utilizing One-Hot Coding method to prepare the dataset for Machine Learning algorithms.

'Casual' column was derived, if the user is a member the value will be 0, otherwise 1.

Created a column using 'day_name' function:

<img width="416" alt="image" src="https://github.com/user-attachments/assets/daa74474-34fd-4db9-aa62-358b1b32d732" />

Created an 'hour' column using python inside Dataiku

<img width="550" alt="image" src="https://github.com/user-attachments/assets/e6611bf9-a4b6-4a1b-ae45-72bcaa0c1468" />

Removed outliers from a specific column in the dataframe using the IQR method:

![image](https://github.com/user-attachments/assets/2fb6604d-e18e-48df-ab5a-eab5baca7ae2)

## Machine Learning Alghorithms

Then I split the combined dataset into training and test subsets and used Linear Regression, Decision Tree Regression, Random Forest Regression and XGBoost to predict if a user is a member or casual user.

Random Forest was the most successful predictor with 67.2% success ratio.

# Data Visualization

In the first graph, we see that the seasons have quite a huge impact on users' total count of rides, and casual users are affected more, as can be expected.

<img width="1337" alt="image" src="https://github.com/user-attachments/assets/e3b6a3e6-b576-4230-bd00-5631b64a4a25" />

In the second graph (below) we see that although the members' ride count thouroughout the week stay almost constant, casual users tend to have more than double on Sundays com when compared to the first 4 days of the week.

<img width="1259" alt="image" src="https://github.com/user-attachments/assets/90983c6b-686d-449d-89a2-b6347ad8fb09" />

In the the third graph we see that at 5 pm the demand is at its peak for both the members and the casual users.

<img width="1082" alt="image" src="https://github.com/user-attachments/assets/165cfa35-d4e2-4da4-824f-a9a719cb3086" />

In the fourth one we have ride duration in terms of seconds on y-axis and and casual and member on x-axis, we see that casual users tend to have longer lasting rides.

<img width="1106" alt="image" src="https://github.com/user-attachments/assets/bcd02fc5-1481-484b-bbbe-9ab6fc2fd273" />

In the fifth graph we see the most popular stations, we see that casual users show great interest in 'Streeter Dr & Grand Ave' and 'Theater on the Lake' stations during the weekend.

<img width="1343" alt="image" src="https://github.com/user-attachments/assets/56b7c7b7-45ad-44b9-a6dc-84e57fc05c8e" />

In the sixth one we see a scatter map of stations and the density of blue collar indicate the amplitude of demand, green lines indicate bike friendly roads (it is a layer in google maps). 

<img width="1338" alt="image" src="https://github.com/user-attachments/assets/efe92647-498c-4f22-97fe-e8538672b85f" />

When we zoom in on the most in-demand area, spanning longitudes from -87.60 to -87.65 and latitudes from 41.90 to 41.85, we can see the names of the roads up close

<img width="1341" alt="image" src="https://github.com/user-attachments/assets/fe1344dc-1370-42e9-a992-ea5fda3346e7" />

# Conclusions:

## Suggestions:​

### Seasonal Offers:​

Winter discounts to encourage off-season membership sign-ups.​

### Flexible Membership Options:​

Introduce short-term or weekend-only memberships targeting leisure-oriented riders.​

### Leverage Data on Popular Stations:​

Launch localized campaigns near high-usage stations to target casual users at the point of engagement.​

### Highlight Cost Savings:​

Compare casual vs. member pricing over time to demonstrate significant savings for frequent riders.​

### Enhanced Member Perks:​

Offer benefits like free extended rides, exclusive promotions, or partner discounts to make membership more appealing.​













