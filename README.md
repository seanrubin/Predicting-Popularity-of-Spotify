# Predicting-Popularity-of-Spotify

The purpose of this project is to utilize the Spotify tracks dataset to develop a model that can predict the popularity of a song. This model will assist future artists and musicians by providing insights into what factors contribute to a song's popularity.

### Data Collection
We first went to look for data that would have the most popular streamed songs on Spotify
We gathered this dataset from Kaggle

This can be found in the Github as dataset.csv

![image](https://github.com/user-attachments/assets/a2e0e9d7-c0ae-4576-b96e-954e3e10042e)

### Data Cleaning
The data was then cleaned to only look at the specific elements we wanted and to drop the ones we did not. Any rows that had a missing entry were taken out as to not ruin the process and the rest of the data. Also, any duplicate entries were taken out as well in order to not sway the results unrealistically. Finally, we had lessened the amount of rows to only 10,000 entries (was previously over 15,000) to remove any outliers and to get a more focused result.
This cleaned up dataset can be found in the Github as spotify_data_trimmed2.csv.

### Starting Analysis
Before we began the process of creating the model, we wanted to see some relationships between the columns so we could have a better idea of what the data was and how to go about achieving our goal. First we created a correlation matrix to see the relationships between the columns.

![image](https://github.com/user-attachments/assets/a8b45025-64ab-46ea-aa59-51b50b1605fc)

We then created scatter plots to show a more in-depth relationship between popularity and three columns that we believed were the most relevant at the time. These three columns were danceability, duration, and energy respectively.

![image](https://github.com/user-attachments/assets/5d3248aa-f834-4406-8962-728541537913)

![image](https://github.com/user-attachments/assets/29a3e868-45aa-4483-981c-2898fc9b153d)

![image](https://github.com/user-attachments/assets/29e0591c-545e-480b-89a6-5b95798b02aa)

As you can see from these scatter plots the data seems to be all over the place but there are some inferences that can be taken from these findings. Both the danceability and energy scatter plots appear to follow a positive correlation. Conversely, the duration scatter plot has a more identifiable negative correlation. From this we can make a rough estimation that the shorter a song is and the higher energy it has, the more popular it appears to be.
