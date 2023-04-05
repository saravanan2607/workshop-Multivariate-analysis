# workshop-Multivariate-analysis
# AIM:
To perform multivarient analysis on the given data set.

# ALGORITHM:
1.Clean the data

2.Remove outliers

3.Apply the skew function and Kurtosis

4.Apply Bivariate analysis on numerical and categorical

5.Apply Multivariate analysis.

# CODE:
## BIVARIATE ANALYSIS:
``` py
import pandas as pd
import numpy as np
import seaborn as sns
import matplotlib.pyplot as plt
df = pd.read_excel("/content/FlightInformation.xlsx")
df
df.info()
df.isnull().sum()
df['Route']=df['Route'].fillna(df['Route'].mode()[0])
df['Total_Stops']=df['Total_Stops'].fillna(df['Total_Stops'].mode()[0])
df.isnull().sum()
df.shape
df.kurtosis()
df.skew()
sns.boxplot(x=df['Price'],y=df['Source'],data=df)
sns.scatterplot(x=df["Price"],y=df["Duration"],data=df)
sns.displot(df,x="Source",hue="Destination")
sns.barplot(x=df['Price'],y=df['Source'],data=df)

```
## MULTIVARIATE ANALYSIS:
``` py
plt.figure(figsize=(17,7))
sns.scatterplot(x=df['Price'], y=df['Source'],hue=df['Source'])
states=df.loc[:,["Dep_Time","Price"]]
states=states.groupby(by=["Dep_Time"]).sum().sort_values(by="Price")
plt.figure(figsize=(17,7))
sns.barplot(x=states.index,y="Price",data=states)
plt.xticks(rotation = 90)
plt.xlabel=("Dep_Time")
plt.ylabel=("Price")
plt.show()
states=df.loc[:,["Airline","Price"]]
states=states.groupby(by=["Airline"]).sum().sort_values(by="Price")
plt.figure(figsize=(17,7))
sns.barplot(x=states.index,y="Price",data=states)
plt.xticks(rotation = 90)
plt.xlabel=("Airline")
plt.ylabel=("Price")
plt.show()
df.corr(method='pearson')
sns.heatmap(df.corr(),annot=True)
```
# OUTPUT:
## BIVARIATE ANALYSIS:
### Data Set:
![1](https://user-images.githubusercontent.com/118661118/229878843-a5a3faaa-b42b-4bac-8169-ec1d1b4cbd2f.png)
### INFO:
![2](https://user-images.githubusercontent.com/118661118/229879021-4abb6941-9bf4-4692-aaa0-e7a25fffc19d.png)
### NULL VALUES:
![3](https://user-images.githubusercontent.com/118661118/229879067-dff8a8da-0665-4a71-b41a-88529228c0c2.png)
### AFTER CLEANING:
![4](https://user-images.githubusercontent.com/118661118/229879149-77e28c2d-7b76-45f8-9669-54ef025d3617.png)
### SHAPE:
![5](https://user-images.githubusercontent.com/118661118/229879190-b2fb48b5-eb45-46b2-9c7e-577e7ad94e3c.png)
### SKEW:
![6](https://user-images.githubusercontent.com/118661118/229879385-4d3acf48-fc6c-48e3-8627-95c49b0f4cbb.png)
### KURTOSIS:
![7](https://user-images.githubusercontent.com/118661118/229879492-9a8878d3-bbab-4d9d-85c3-4ef189dd1ae3.png)
### NUMERICAL & NUMERICAL:
#### SCATTERPLOT:
![9](https://user-images.githubusercontent.com/118661118/229879641-7a232c41-cbb5-4210-94a9-88d78e41d11d.png)
### NUMERICAL & CATEGORICAL:
#### BOXPLOT:
![8](https://user-images.githubusercontent.com/118661118/229879893-21ad749d-714a-49bd-91a3-4055c69a12b5.png)
#### DISPLOT:
![10](https://user-images.githubusercontent.com/118661118/229879931-a66b109f-901f-477d-9c58-71dd36e45561.png)
#### BARPLOT:
![11](https://user-images.githubusercontent.com/118661118/229880023-24b954bd-1e49-473b-a0fb-5eb03dc28909.png)

## MULTIVARIATE ANALYSIS:
### PRICE & SOURCE:
![12](https://user-images.githubusercontent.com/118661118/229880408-cb81d62d-e0cd-4a66-8405-f86c459606d3.png)
### PRICE & DEP_TIME:
![13](https://user-images.githubusercontent.com/118661118/229880574-a05f4bd9-3b5c-452b-beeb-c12222294900.png)
### PRICE & AIRLINE:
![14](https://user-images.githubusercontent.com/118661118/229880637-98728ad2-5512-4c65-bd61-4fa1f873f0da.png)
### CORR():
![15](https://user-images.githubusercontent.com/118661118/229880710-2d327046-52ad-4741-b177-2f2cd161a903.png)
### HEATMAP:
![Screenshot 2023-04-04 232117](https://user-images.githubusercontent.com/118661118/229880761-fefcb58c-a907-41cf-bce8-19787f365fb4.png)

# RESULT:
Thus the Bivariate and Multivariate analysis is observerd for the given data set.




