# Exno:1
Data Cleaning Process

# AIM
To read the given data and perform data cleaning and save the cleaned data to a file.

# Explanation
Data cleaning is the process of preparing data for analysis by removing or modifying data that is incorrect ,incompleted , irrelevant , duplicated or improperly formatted. Data cleaning is not simply about erasing data ,but rather finding a way to maximize datasets accuracy without necessarily deleting the information.

# Algorithm
STEP 1: Read the given Data

STEP 2: Get the information about the data

STEP 3: Remove the null values from the data

STEP 4: Save the Clean data to the file

STEP 5: Remove outliers using IQR

STEP 6: Use zscore of to remove outliers

# Coding and Output

![Screenshot 2024-03-04 101448](https://github.com/DurgaV240106/exno1/assets/144870878/8d6dcf2c-6327-41e1-be6f-a28c94625b40)

df.head()

![Screenshot 2024-03-05 000523](https://github.com/DurgaV240106/exno1/assets/144870878/1bc424ed-3ecd-45d8-b971-b1653ecfe6f8)

df.tail()

![Screenshot 2024-03-05 000634](https://github.com/DurgaV240106/exno1/assets/144870878/f1a215ff-497f-42d8-9cb7-e2d93b881472)

df.describe()

![Screenshot 2024-03-05 000722](https://github.com/DurgaV240106/exno1/assets/144870878/87888bee-8660-4486-8b3f-2e57c164d6b5)

df.info()

![Screenshot 2024-03-05 000830](https://github.com/DurgaV240106/exno1/assets/144870878/9ed702a3-35ca-4cf6-a9f6-8d74d4f2c8c6)

df.shape

![Screenshot 2024-03-05 000929](https://github.com/DurgaV240106/exno1/assets/144870878/b6dd1359-d8ef-417e-8600-dbda14e9d545)

df.isnull().sum()

![Screenshot 2024-03-05 001015](https://github.com/DurgaV240106/exno1/assets/144870878/25da7b28-058c-4486-971a-56daae79f10e)

df.nunique()

![Screenshot 2024-03-05 001058](https://github.com/DurgaV240106/exno1/assets/144870878/2b55fac7-c302-416f-94e4-81606bcfd1c2)

mn=df.TOTAL.mean() mn

![Screenshot 2024-03-05 001137](https://github.com/DurgaV240106/exno1/assets/144870878/4282acb7-82ae-4d52-8b4b-3940e2bc6765)

df.TOTAL.fillna(mn,inplace=True) df

![Screenshot 2024-03-05 001225](https://github.com/DurgaV240106/exno1/assets/144870878/0f99ab8e-8586-4936-927c-a26350c4033a)

a=df.M4.min() a

![Screenshot 2024-03-05 001257](https://github.com/DurgaV240106/exno1/assets/144870878/f23b315f-30c0-453d-93b5-0c868d830dab)

df.M4.fillna(a,inplace=True) df

![Screenshot 2024-03-05 001339](https://github.com/DurgaV240106/exno1/assets/144870878/1d8952b2-ba8b-4301-b9bd-f09c437c7543)

import pandas as pd import seaborn as sns import numpy as np
age=[1,3,28,27,25,92,30,39,40,50,26,24,29,94] af=pd.DataFrame(age) af

![Screenshot 2024-03-05 001428](https://github.com/DurgaV240106/exno1/assets/144870878/41b12962-c640-4aba-b667-739f63d9263b)

sns.boxplot(data=af)

![Screenshot 2024-03-05 001511](https://github.com/DurgaV240106/exno1/assets/144870878/3581ffcd-efeb-4c84-acfd-4aa6b03e17f1)

q1=af.quantile(0.25) q2=af.quantile(0.5) q3=af.quantile(0.75) iqr=q3-q1 iqr

![Screenshot 2024-03-05 001553](https://github.com/DurgaV240106/exno1/assets/144870878/4cc5b1f3-be01-45e7-b955-97f8d3cbefb4)

Q1=np.percentile(af,25) Q3=np.percentile(af,75) IQR=Q3-Q1 IQR

![Screenshot 2024-03-05 001651](https://github.com/DurgaV240106/exno1/assets/144870878/c2d8ed1a-efec-42a7-8693-ae01a458ae5a)

lower_bound=Q1-1.5IQR upper_bound=Q3+15*IQR outliers=[x for x in age if x<lower_bound 
or x>upper_bound] print("Q1:",Q1) print("Q3:",Q3) print("IQR:",IQR) print("lower")

![Screenshot 2024-03-05 001837](https://github.com/DurgaV240106/exno1/assets/144870878/4845eaf7-bcb8-4589-be4b-ad52e3b32906)

af=af[((af>=lower_bound)&(af<=upper_bound))] af

![Screenshot 2024-03-05 001922](https://github.com/DurgaV240106/exno1/assets/144870878/4e917c1a-89a2-4b1a-83a9-a36296cf91ab)

af.dropna()

![Screenshot 2024-03-05 001956](https://github.com/DurgaV240106/exno1/assets/144870878/4f64c2fd-d4a4-4068-b667-23e6485e7a9e)
sns.boxplot(data=af)

![Screenshot 2024-03-05 002049](https://github.com/DurgaV240106/exno1/assets/144870878/60197a06-e29e-43af-a3ea-bd042a5cd28d)

data=[1,12,15,18,21,24,27,30,33,36,39,42,45,48,51,54,57,60,63,66,69,72,75,78,81,84,87,90,93,96,99,102,105] 
df=pd.DataFrame(data) df

![Screenshot 2024-03-05 002146](https://github.com/DurgaV240106/exno1/assets/144870878/115127b8-3ea2-4d08-b17d-d6fb25bb7b55)

import numpy as np from scipy import stats z=np.abs(stats.zscore(df)) z

![Screenshot 2024-03-05 002230](https://github.com/DurgaV240106/exno1/assets/144870878/9ddf0056-936e-499c-9c55-3954b5e70662)























# Result
          Thus the given program executed successfully.
