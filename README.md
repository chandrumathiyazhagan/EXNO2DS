# EXNO2DS
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
```python
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns

dt=pd.read_csv("/content/titanic_dataset.csv")

dt
 ```
![Screenshot 2024-03-15 231523](https://github.com/chandrumathiyazhagan/EXNO2DS/assets/119393023/2a1b8b69-b138-4cc7-899c-1171fa3d7eea)
```python
dt.info
```
![Screenshot 2024-03-15 231532](https://github.com/chandrumathiyazhagan/EXNO2DS/assets/119393023/23f1e963-f5b0-4d38-81ac-1a5a43fe8c85)
```python
dt.set_index("PassengerId",inplace=True)

dt.describe()
```
![Screenshot 2024-03-15 231539](https://github.com/chandrumathiyazhagan/EXNO2DS/assets/119393023/ec0a1257-120f-4ce6-a1d8-6ed8f0b6874d)
 ```python
dt.shape
```
![Screenshot 2024-03-15 231547](https://github.com/chandrumathiyazhagan/EXNO2DS/assets/119393023/3f9d7819-6a01-45a7-a415-e0383bb89a2a)
```python
dt.nunique()
```
![Screenshot 2024-03-15 231552](https://github.com/chandrumathiyazhagan/EXNO2DS/assets/119393023/cfa1d74e-d078-4a30-ac7b-4e636ebc86b1)
 ```python
dt["Survived"].value_counts()

per=(dt["Survived"].value_counts()/dt.shape[0]*100).round(2)
per
 ```
 ![Screenshot 2024-03-15 231559](https://github.com/chandrumathiyazhagan/EXNO2DS/assets/119393023/b1285c08-04e3-4fc2-9768-316a8c39cd6a)
```python
sns.countplot(data=dt,x="Survived")
```
![Screenshot 2024-03-15 231606](https://github.com/chandrumathiyazhagan/EXNO2DS/assets/119393023/7d33f005-b256-4619-90b3-1ea0cee2bae7)
 ```python
dt

dt.Pclass.unique()
```
![Screenshot 2024-03-15 231617](https://github.com/chandrumathiyazhagan/EXNO2DS/assets/119393023/d9c2de6d-8526-4fe4-bc16-a60851b2bb4e)
```python
dt.rename(columns={'Sex':'Gender'},inplace=True)
dt
```
![Screenshot 2024-03-15 231625](https://github.com/chandrumathiyazhagan/EXNO2DS/assets/119393023/93b09703-8c88-4a21-94d1-a7514c7ee401)
 ```python
sns.catplot(x="Gender",col="Survived",kind="count",data=dt,height=5,aspect=.7)
```
![Screenshot 2024-03-15 231632](https://github.com/chandrumathiyazhagan/EXNO2DS/assets/119393023/85af7c68-0a92-4df4-a5da-e291d0a115a0)
```python
sns.catplot(x='Survived',hue="Gender",data=dt,kind="count")
```
![Screenshot 2024-03-15 231641](https://github.com/chandrumathiyazhagan/EXNO2DS/assets/119393023/763abb17-b9c4-4fe2-ad9f-3e95b2a959f2)
```python
dt.boxplot(column="Age",by="Survived")
```
![Screenshot 2024-03-15 231647](https://github.com/chandrumathiyazhagan/EXNO2DS/assets/119393023/fb967ba2-c989-4957-b8ba-d0fbf3719b3c)
```python
sns.scatterplot(x=dt["Age"],y=dt["Fare"])
```
![Screenshot 2024-03-15 231653](https://github.com/chandrumathiyazhagan/EXNO2DS/assets/119393023/90ef5e43-711e-4501-aa2f-1f6de4dccc9d)
 ```python
sns.jointplot(x="Age",y="Fare",data=dt)
 ```
![Screenshot 2024-03-15 231659](https://github.com/chandrumathiyazhagan/EXNO2DS/assets/119393023/58e46e38-37d9-404a-a8cf-cdf9e1c8acf5)
```python
fig,ax1 = plt.subplots(figsize=(8,5))
pt=sns.boxplot(ax=ax1,x='Pclass',y='Age',hue='Gender',data=dt)
```
![Screenshot 2024-03-15 231706](https://github.com/chandrumathiyazhagan/EXNO2DS/assets/119393023/8623a8ea-47a6-4022-aa20-11ab0e36f840)
```python
sns.catplot(data=dt,col = "Survived",x = "Gender",hue="Pclass",kind = "count")
```
![Screenshot 2024-03-15 231712](https://github.com/chandrumathiyazhagan/EXNO2DS/assets/119393023/b1037acd-c2c6-4449-b2b4-66772081ede7)
```python
corr = dt.corr()
sns.heatmap(corr,annot=True)
```
![Screenshot 2024-03-15 231725](https://github.com/chandrumathiyazhagan/EXNO2DS/assets/119393023/f7b363c2-463b-47e4-b4cc-7672a906233b)
```python
     sns.pairplot(dt)
 ```
![Screenshot 2024-03-15 231742](https://github.com/chandrumathiyazhagan/EXNO2DS/assets/119393023/7b373422-21da-4513-b779-f8f3132d1a8c)

# RESULT
          Hence the performing Exploratory Data Analysis on the given data set is successful.
