# Predicting-Popularity-of-Spotify

The purpose of this project is to utilize the Spotify tracks dataset to develop a model that can predict the popularity of a song. This model will assist future artists and musicians by providing insights into what factors contribute to a song's popularity.

## Data Collection
We first went to look for data that would have the most popular streamed songs on Spotify
We gathered this dataset from Kaggle

This can be found in the Github as dataset.csv

![image](https://github.com/user-attachments/assets/a2e0e9d7-c0ae-4576-b96e-954e3e10042e)

## Data Cleaning
The data was then cleaned to only look at the specific elements we wanted and to drop the ones we did not. Any rows that had a missing entry were taken out as to not ruin the process and the rest of the data. Also, any duplicate entries were taken out as well in order to not sway the results unrealistically. Finally, we had lessened the amount of rows to only 10,000 entries (was previously over 15,000) to remove any outliers and to get a more focused result.
This cleaned up dataset can be found in the Github as spotify_data_trimmed2.csv.

## Starting Analysis
Before we began the process of creating the model, we wanted to see some relationships between the columns so we could have a better idea of what the data was and how to go about achieving our goal. First we created a correlation matrix to see the relationships between the columns.

![image](https://github.com/user-attachments/assets/a8b45025-64ab-46ea-aa59-51b50b1605fc)

We then created scatter plots to show a more in-depth relationship between popularity and three columns that we believed were the most relevant at the time. These three columns were danceability, duration, and energy respectively.

![image](https://github.com/user-attachments/assets/5d3248aa-f834-4406-8962-728541537913)

![image](https://github.com/user-attachments/assets/29a3e868-45aa-4483-981c-2898fc9b153d)

![image](https://github.com/user-attachments/assets/29e0591c-545e-480b-89a6-5b95798b02aa)

As you can see from these scatter plots the data seems to be all over the place but there are some inferences that can be taken from these findings. Both the danceability and energy scatter plots appear to follow a positive correlation. Conversely, the duration scatter plot has a more identifiable negative correlation. From this we can make a rough estimation that the shorter a song is and the higher energy it has, the more popular it appears to be.

These visualizations as well as the code to get them are in the Github as Music_Popularity_Analysis.ipynb.

## Narrowing Down Our Search
After some more testing we had determined that to get a more accurate model it would be helpful to narrow down the data entries we worked with. We decided to only look at the seventy-fifth percentile when running our model. We had determined that to be 71.0.

![image](https://github.com/user-attachments/assets/f7bb2f02-f06d-4210-b0d5-8212afd4b7d7)

We then went to get a basic look at the most popular songs as a starting reference. The popularity has one hundred as the maximum.

![image](https://github.com/user-attachments/assets/84b43c2a-5667-4c0e-9f2a-4aea55545055)

We then wanted to determine the most frequent genre of these popular songs. We wanted to learn this at this stage due to the fact that this column is not numerical and has too many variations to be converted to binary and therefore would not be able to fit in the model. We can see from the results that dance is the most popular genre with k-pop and alt-rock following.

![image](https://github.com/user-attachments/assets/fee36be8-6efd-405b-8ad4-7a9be68cef39)

These queries were created in Google Colab and can be found in the Github as SpotifySpark.ipynb.

## Running The Model
To create the model, we set the y variable to be the popularity values above 71 (the 75th percentile) and the x variable to the rest of the columns with integer values. We created three layers with 80, 30, and 1 units and we came to these numbers after testing and finding that these gave us the most desirable results. We then ran the model for 20 epochs and got an accuracy of 75.65%.

![image](https://github.com/user-attachments/assets/0eb1ba28-156d-4e07-b8c9-5e68ebd5a25d)

![image](https://github.com/user-attachments/assets/b1c7fe8b-b6ed-4152-a2c2-98d5b7afb644)

We then went back to spark to find a random entry to test this on. We found the average entry by popularity and put all of the data from that into our model. The result we were given was a 16.2% predicted popularity.

![image](https://github.com/user-attachments/assets/7e84c935-67d6-464f-a621-e59b92d99281)

We than ran a classification report.

![image](https://github.com/user-attachments/assets/807edb0d-6885-48f1-a8e5-359ab639b9b8)

All this code can be found in the Github under spotify_model.ipynb.

## What We've Learned
This model is a good stepping stone to finding what makes a song popular on Spotify. This, however, is not the end all be all on how to create popular and successful music. If that was the case the music industry would have been using something along these lines for decades. There are a lot more aspects to popular music than just the statistics such as the sound, exposure and the intangible “IT Factor”. As stated this model is a good way to look at what is and isn’t seen as popular and to steer someone in the right direction to create a hit streaming song.


