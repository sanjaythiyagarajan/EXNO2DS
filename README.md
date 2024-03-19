# EXNO2DS-Exploratory Data Analysis
## AIM:
  To perform Exploratory Data Analysis on the given data set.
      
## EXPLANATION:
 The primary aim with exploratory analysis is to examine the data for distribution, outliers and anomalies to direct specific testing of your hypothesis.
  
## ALGORITHM:
STEP 1: Import the required packages to perform Data Cleansing,Removing Outliers and Exploratory Data Analysis.

STEP 2: Replace the null value using any one of the method from mode,median and mean based on the dataset available.

STEP 3: Use boxplot method to analyze the outliers of the given dataset.

STEP 4: Remove the outliers using Inter Quantile Range method.

STEP 5: Use Countplot method to analyze in a graphical method for categorical data.

STEP 6: Use displot method to represent the univariate distribution of data.

STEP 7: Use cross tabulation method to quantitatively analyze the relationship between multiple variables.

STEP 8: Use heatmap method of representation to show relationships between two variables, one plotted on each axis.

## CODING AND OUTPUT
### Developed by: SANJAY T
### Register no: 212222110039
```py
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns  
df=pd.read_csv("titanic_dataset.csv")
df
```
![image](https://github.com/sanjaythiyagarajan/EXNO2DS/assets/119409242/73487bfc-d116-4c2c-a2cb-148803714f14)



```py
df.info()
```
![image](https://github.com/sanjaythiyagarajan/EXNO2DS/assets/119409242/06604b25-d428-4231-b382-80f1ca7e4b97)



```py
df.shape
```
![image](https://github.com/sanjaythiyagarajan/EXNO2DS/assets/119409242/27279562-a2e4-4d5c-ba9a-071c78dd0f7a)



```py
df.set_index("PassengerId",inplace=True)
df.describe()
```
![image](https://github.com/sanjaythiyagarajan/EXNO2DS/assets/119409242/5975035f-23c5-44a0-800a-bbdc477e68ea)



```py
df.shape
```


### Categorical data analysis
```py
df.nunique()
```

![image](https://github.com/sanjaythiyagarajan/EXNO2DS/assets/119409242/fbed7ca0-0e20-4986-ba0a-3affe1ff14cd)


```py
df["Survived"].value_counts()
```

![image](https://github.com/sanjaythiyagarajan/EXNO2DS/assets/119409242/8dc9357a-5211-4983-8b99-4ee368723391)


```py
per=(df["Survived"].value_counts()/df.shape[0]*100).round(2)
per
```
![image](https://github.com/sanjaythiyagarajan/EXNO2DS/assets/119409242/33dc54d2-9716-4bc3-a516-22ab97e0183b)

```py
sns.countplot(data=df,x="Survived")
```
![image](https://github.com/sanjaythiyagarajan/EXNO2DS/assets/119409242/adc8147c-269a-4576-946a-818b6bd787ea)

```py
df
```
![image](https://github.com/sanjaythiyagarajan/EXNO2DS/assets/119409242/434aaa0c-fa83-4b13-84aa-9e4f54ea9159)

```py
df.Pclass.unique()
```
![image](https://github.com/sanjaythiyagarajan/EXNO2DS/assets/119409242/858ff6f0-ab5d-42a8-ad4a-67cbcc6b55b9)


```py
df.rename(columns={'Sex':'Gender'},inplace=True)
df
```
![image](https://github.com/sanjaythiyagarajan/EXNO2DS/assets/119409242/11441fd8-31cc-4d9a-8dda-b88882d51879)


### Bivariate Analysis
```py
sns.catplot(x="Gender",col="Survived",kind="count",data=df,height=5,aspect=.7)
```
![image](https://github.com/sanjaythiyagarajan/EXNO2DS/assets/119409242/17fdcf8f-bbfd-4154-893d-d0a5116a7234)


```py
sns.catplot(x="Survived",hue="Gender",data=df,kind="count")
```
![image](https://github.com/sanjaythiyagarajan/EXNO2DS/assets/119409242/323885ad-e81a-4f32-ba82-736f8b3b54fb)


```py
df.boxplot(column="Age",by="Survived")
```

![image](https://github.com/sanjaythiyagarajan/EXNO2DS/assets/119409242/34904ed9-73d7-48f8-845a-8a45b6c4babc)



```py
sns.scatterplot(x=df["Age"],y=df["Fare"])
```

![image](https://github.com/sanjaythiyagarajan/EXNO2DS/assets/119409242/82ea4e6b-9698-47bc-ae7b-0dc202c1bd84)


```py
sns.jointplot(x="Age",y="Fare",data=df)
```
![image](https://github.com/sanjaythiyagarajan/EXNO2DS/assets/119409242/018711e1-b7d4-4eb3-b6ee-ec0a9e9176bb)


### Multivariate Analysis
```py
fig, ax1 = plt.subplots(figsize=(8,5))
plt = sns.boxplot(ax=ax1,x='Pclass',y='Age',hue='Gender',data=df)
```
![image](https://github.com/sanjaythiyagarajan/EXNO2DS/assets/119409242/5c0f6a5e-3238-4c34-8c1e-f657b9c9f044)


```py
sns.catplot(data=df,col="Survived",x="Gender",hue="Pclass",kind="count")
```

![image](https://github.com/sanjaythiyagarajan/EXNO2DS/assets/119409242/b68752bb-a874-4bd6-9629-8210ca8e50a6)


# Co-relation
```py
corr=df.corr()
sns.heatmap(corr,annot=True)
```

![image](https://github.com/sanjaythiyagarajan/EXNO2DS/assets/119409242/2b4bb445-3f33-4899-a90b-5d7c4c9a006d)


```py
sns.pairplot(df)
```
![image](https://github.com/sanjaythiyagarajan/EXNO2DS/assets/119409242/670a4bca-b431-4848-a85c-ae11130b9fd2)


## RESULT
We have performed Exploratory Data Analysis on the given data set successfully.
