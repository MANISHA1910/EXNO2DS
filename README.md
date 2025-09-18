# EXNO2DS
# NAME : MANISHA.M
# REG NO :212224220061
# DATE : 18.09.2025
# AIM:
      To perform Exploratory Data Analysis on the given data set.
      
# EXPLANATION:
  The primary aim with exploratory analysis is to examine the data for distribution, outliers and anomalies to direct specific testing of your hypothesis.
  
# ALGORITHM:
STEP 1: Import the required packages to perform Data Cleansing,Removing Outliers and Exploratory Data Analysis.

STEP 2: Replace the null value using any one of the method from mode,median and mean based on the dataset available.

STEP 3: Use boxplot method to analyze the outliers of the given dataset.

STEP 4: Remove the outliers using Inter Quantile Range method.

STEP 5: Use Countplot method to analyze in a graphical method for categorical data.

STEP 6: Use displot method to represent the univariate distribution of data.

STEP 7: Use cross tabulation method to quantitatively analyze the relationship between multiple variables.

STEP 8: Use heatmap method of representation to show relationships between two variables, one plotted on each axis.

## CODING AND OUTPUT
```
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
df=pd.read_csv("/content/titanic_dataset.csv")
df
```
# OUTPUT
<img width="1744" height="822" alt="image" src="https://github.com/user-attachments/assets/02ef4b12-7a28-4c60-bd9a-ab2463b7e0c4" />

```
df.info()
```
# OUTPUT

<img width="782" height="538" alt="image" src="https://github.com/user-attachments/assets/4f273c7f-88d6-4d4f-8a2a-e573924ef5d1" />

```
df.describe()
```
# OUTPUT
<img width="1269" height="482" alt="image" src="https://github.com/user-attachments/assets/87afc853-6969-45be-9e06-3a713e7b1121" />


```
df.dtypes
```
# OUTPUT 
<img width="744" height="708" alt="image" src="https://github.com/user-attachments/assets/c169ec20-a147-46e4-9f62-23bafefa6306" />

```
df.shape
```
# OUTPUT
<img width="586" height="128" alt="image" src="https://github.com/user-attachments/assets/7100c6d3-d137-47fa-b9f2-ad8fe2251ada" />

```
df.value_counts()
```
# OUTPUT

<img width="1758" height="676" alt="image" src="https://github.com/user-attachments/assets/ce57e5a8-8a30-4cd0-b024-cf22d013b84e" />

```
df['Age'].value_counts()
```
# OUTPUT

<img width="1515" height="762" alt="image" src="https://github.com/user-attachments/assets/797723c6-9783-496f-9673-79b731cc19f9" />

```
df.set_index("PassengerId", inplace=True)
df
```
# OUTPUT

<img width="1780" height="722" alt="image" src="https://github.com/user-attachments/assets/bc07ed6b-7f3c-4083-be4f-d6f11a548f5c" />

```
df.nunique()
```
# OUTPUT

<img width="1705" height="648" alt="image" src="https://github.com/user-attachments/assets/eadc3954-3a9a-4243-8f27-19c01bc37c03" />

```
sns.countplot(data=df,x='Survived')
```
# OUTPUT

<img width="927" height="720" alt="image" src="https://github.com/user-attachments/assets/49e1ea5a-50a4-4d49-9224-00a7548059ef" />

```
df.rename(columns={'Sex':'Gender'},inplace=True)
df
```
# OUTPUT


<img width="1719" height="735" alt="image" src="https://github.com/user-attachments/assets/c4bb825d-deb4-4250-bc8b-11b688f6205b" />

```
sns.catplot(x="Gender",col="Survived",kind="count",data=df,height=5,aspect=.7)
```
# OUTPUT

<img width="1454" height="774" alt="image" src="https://github.com/user-attachments/assets/f81f2ee1-8cf1-4b78-ab3c-4ccceff959d9" />

```
df.boxplot(column="Age",by="Survived")
```
# OUTPUT

<img width="911" height="717" alt="image" src="https://github.com/user-attachments/assets/c46b4755-b9f7-41d1-b2e4-d065d1b5a024" />

```
sns.scatterplot(x=df["Age"],y=df["Fare"])
```
# OUTPUT

<img width="1169" height="710" alt="image" src="https://github.com/user-attachments/assets/0094d053-6ae2-4ed3-b579-82f4b9f4c206" />
```
fig, axl=plt.subplots(figsize=(8,5))
 plt=sns.boxplot(ax=axl,x='Pclass',y='Age',hue='Gender',data=df)
```
# OUTPUT

<img width="1155" height="643" alt="image" src="https://github.com/user-attachments/assets/30c04dd4-4527-49ab-98dc-3528f0076641" />


```
plt=sns.boxplot(x='Pclass',y='Age',hue='Gender',data=df)
```

# OUTPUT

<img width="994" height="677" alt="image" src="https://github.com/user-attachments/assets/733556f6-c647-4168-96ab-02c257c6e160" />

```
import seaborn as sns
sns.catplot(x='Pclass',y="Age",hue="Gender",col="Survived",kind="box",data=df)
```
# OUTPUT

<img width="1650" height="719" alt="image" src="https://github.com/user-attachments/assets/54e02655-0e72-48ca-b304-8fbf29775201" />

```
sns.catplot(data=df,col="Survived",x="Gender",hue='Pclass',kind="count")
```
# OUTPUT 

<img width="1684" height="771" alt="image" src="https://github.com/user-attachments/assets/8ef37934-d3f7-4ffe-a6c5-116ebd46ce36" />

```
corr=df.corr(numeric_only=True)
 sns.heatmap(corr,annot=True)
```
# OUTPUT

<img width="956" height="704" alt="image" src="https://github.com/user-attachments/assets/32dc0649-461c-47b0-a94c-1011c1c577b1" />

```
corr=df.select_dtypes(include=np.number).corr()
sns.heatmap(corr,annot=True)
```
# OUTPUT

<img width="1009" height="735" alt="image" src="https://github.com/user-attachments/assets/f94d9d25-e245-4f75-b80a-efacca7692bf" />

# RESULT
Successfully Executed
