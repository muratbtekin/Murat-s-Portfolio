# Murat-s-Portfolio
Analytics Portfolio

What was asked?

Director of the marketing believes that the company's success depend on converting casual users to annual members. Hence she asks me (I am a junior data analyst) to provide insights through data visualizations in order to convince the executive team.

The details are to be found here: https://artscience.ai/divvy-dataviz-case-study/

Gathering the Data

In this project I first downloaded the datasets from here https://www.kaggle.com/datasets/bchen02/google-data-analytics-certificate-bike-share](https://divvy-tripdata.s3.amazonaws.com/index.html

I selected the datasets from August 2020 all the way up to July 2021 so that I could view the change in users' behaviour depeding on seasons.

Combining the Data

I first used Colab, utilizing python to join 12 datasets.

https://colab.research.google.com/drive/1wMdDetjCncKObr7QE2oWTZHytHOvWNW6?usp=sharing

Preparing the Data

Then I changed the data type of started_at and ended_at from object to datetime and subtracted started_at from ended_at to derive the 'duration' column.

Thereafter I dropped the rows where the duration is less than 0.

The rows where 'start_station_name', 'start_station_id', 'end_station_name', 'end_station_id' values were empty, were also dropped to have a more robust dataset.

After the aforementioned steps, I moved on with Dataiku to further process the data, yet I resorted to using Python again when I felt the need to do so.

Using Dataiku's preparation steps, I derived the 'Weekend' column, utilizing One-Hot Coding method to prepare the dataset for Machine Learning algorithms.

I did the same for Electric_Bike and Member columns. If the bike is electric, value will be 1, if it is a docked bike, the value will be 0, if the user is a member, in the respective column the value will be 1, otherwise 0.

Created a column using 'day_name' function:

<img width="416" alt="image" src="https://github.com/user-attachments/assets/daa74474-34fd-4db9-aa62-358b1b32d732" />

Created an 'hour' column using python inside Dataiku

<img width="550" alt="image" src="https://github.com/user-attachments/assets/e6611bf9-a4b6-4a1b-ae45-72bcaa0c1468" />

Removed outliers from a specific column in the dataframe using the IQR method:

![image](https://github.com/user-attachments/assets/2fb6604d-e18e-48df-ab5a-eab5baca7ae2)

Then I split the combined dataset into training and test subsets and used Linear Regression, Decision Tree Regression, Random Forest Regression and XGBoost to predict if a user is a member or casual user.

Random Forest was the most successful predictor with 67.2% success ratio.








