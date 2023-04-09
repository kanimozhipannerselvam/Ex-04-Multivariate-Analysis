# Ex-04-Multivariate-Analysis

AIM

To perform Multivariate EDA on the given data set.
Explanation:

Exploratory data analysis is used to understand the messages within a dataset. This technique involves many iterative processes to ensure that the cleaned data is further sorted to better understand the useful meaning.The primary aim with exploratory analysis is to examine the data for distribution, outliers and anomalies to direct specific testing of your hypothesis.
ALGORITHM:
STEP 1

Import the built libraries required to perform EDA and outlier removal.
STEP 2

Read the given csv file
STEP 3

Convert the file into a dataframe and get information of the data.
STEP 4

Return the objects containing counts of unique values using (value_counts()).
STEP 5

Plot the counts in the form of Histogram or Bar Graph.
STEP 6

Use seaborn the bar graph comparison of data can be viewed.
STEP 7

Find the pairwise correlation of all columns in the dataframe.corr()
STEP 8

Save the final data set into the file
PROGRAM

import pandas as pd

import numpy as np

import seaborn as sns

import matplotlib.pyplot as plt

df=pd.read_csv("SuperStore.csv")

df

df.info()

df.describe()

df.isnull().sum()

df['Postal Code'] = df["Postal Code"].fillna(df['Postal Code'].mode()[0])

df.isnull().sum()

df.dtypes

sns.scatterplot(df['Row ID'],df['Sales'])

states=df.loc[:,["State","Sales"]]

states=states.groupby(by=["State"]).sum().sort_values(by="Sales")

plt.figure(figsize=(17,7))

sns.barplot(x=states.index,y="Sales",data=states)

plt.xticks(rotation = 90)

plt.xlabel=("STATES")

plt.ylabel=("SALES")

plt.show()

states=df.loc[:,["State","Row ID"]]

states=states.groupby(by=["State"]).sum().sort_values(by="Row ID")

plt.figure(figsize=(17,7))

sns.barplot(x=states.index,y="Row ID",data=states)

plt.xticks(rotation = 90)

plt.xlabel=("STATES")

plt.ylabel=("ROW ID")

plt.show()

states=df.loc[:,["Segment","Row ID"]]

states=states.groupby(by=["Segment"]).sum().sort_values(by="Row ID")

sns.barplot(x=states.index,y="Row ID",data=states)

plt.xticks(rotation = 90)

plt.xlabel=("SEGMENT")

plt.ylabel=("ROW ID")

plt.show()

sns.barplot(df['Sales'],df['Ship Mode'],hue=df['Region'])

df.corr()

sns.heatmap(df.corr(),annot=True)

OUTPUT

DATA

![image](https://user-images.githubusercontent.com/119476060/230761062-f26f86ef-281a-4553-be9d-5f07fc1d9d71.png)

DATA INFORMATION

![image](https://user-images.githubusercontent.com/119476060/230761066-639f22b5-dc5a-45e4-b3a7-9c03ce00e31a.png)

DATA DESCRIBE

![image](https://user-images.githubusercontent.com/119476060/230761073-e6453f7f-37bb-4d2b-a1d4-7904ed4fef71.png)

Checking the null values and Cleaning it

![image](https://user-images.githubusercontent.com/119476060/230761086-9e1d17d6-1d1c-41f5-8d79-22a1b304acea.png)

![image](https://user-images.githubusercontent.com/119476060/230761093-31c31564-2be5-4e43-8c4a-35f806e1b6e8.png)

DATA TYPES

![image](https://user-images.githubusercontent.com/119476060/230761365-e92e5040-3ea6-4cac-8526-ebf72530d3bf.png)

SCATTERPLOT

![image](https://user-images.githubusercontent.com/119476060/230761118-b5d89456-6328-4071-88b4-a76ab7f9e783.png)

BARPLOT

![image](https://user-images.githubusercontent.com/119476060/230761124-b9a04844-f403-436d-94bc-b6c32e97d80d.png)

![image](https://user-images.githubusercontent.com/119476060/230761130-6649387a-ff33-4900-a1f2-3e972e62b28c.png)

![image](https://user-images.githubusercontent.com/119476060/230761138-0524c3ff-a2cd-444c-988e-6781be4b0e79.png)

![image](https://user-images.githubusercontent.com/119476060/230761150-d894aac7-9520-42c0-baf0-1bf0659bc090.png)

CORRELATION COEFFICIENT INTERPRETATION

![image](https://user-images.githubusercontent.com/119476060/230761160-a5c7bdde-4f86-4179-870d-aebee6dfb1ca.png)

HEATMAP

![image](https://user-images.githubusercontent.com/119476060/230761184-e15d16ac-ee0d-4659-80d8-bbb75e3f10d3.png)


RESULT

Thus we have read the given data and performed the multivariate analysis with different types of plots.







