# EXNO:02 DS
### NAME : NARRA RAMYA
### REG NO: 212223240128
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
```c
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
df=pd.read_csv("titanic_dataset.csv")
df
```
![image](https://github.com/user-attachments/assets/f5d98124-3373-412b-be88-8c4f80b075d8)
```c
df.info()
```
![image](https://github.com/user-attachments/assets/3110bb31-2a23-4f18-b117-597498e41a6d)

```c
df.shape
```

![image](https://github.com/user-attachments/assets/b5da1cb4-242e-480c-a6c3-4b7b5fe8e2b4)

```c
df.set_index("PassengerId",inplace=True)
df.describe()
```
![image](https://github.com/user-attachments/assets/46ae3007-fdb6-44d6-8357-02a25f709496)

```c
df.shape
```
![image](https://github.com/user-attachments/assets/db96bfe1-dec2-4d79-92e2-49caab17bccd)

```c
df.nunique()
```
![image](https://github.com/user-attachments/assets/0e1f5d1e-7f24-4883-93cf-1459927bb324)

```c
df["Survived"].value_counts()
```
![image](https://github.com/user-attachments/assets/10fe84aa-05b4-4fee-bc01-03b2bb64dce0)
```c
per=(df["Survived"].value_counts()/df.shape[0]*100).round(2)
per
```
![image](https://github.com/user-attachments/assets/3272bc47-498a-4fc4-84e7-18aa98b4a05a)
```c
sns.countplot(data=df,x="Survived")
```
![image](https://github.com/user-attachments/assets/a89fa277-da80-4041-985f-d3748b7bfbae)
```c
df
```
![image](https://github.com/user-attachments/assets/a935377a-1aae-4907-bd91-99cde2237217)

```c
df.Pclass.unique()
```
![image](https://github.com/user-attachments/assets/5ec071e8-4193-4f57-8663-a65386fe6960)
```c
df.rename(columns={'Sex':'Gender'},inplace=True)
df
```
![image](https://github.com/user-attachments/assets/be23b9d9-6a30-4bde-80ac-eb601b398810)
```c
sns.catplot(x="Gender",col="Survived",kind="count",data=df,height=5,aspect=.7)
```
![image](https://github.com/user-attachments/assets/865515dd-2681-4b9f-af44-41bb9c4eeafa)

```c
sns.catplot(x="Survived",hue="Gender",data=df,kind="count")
```
![image](https://github.com/user-attachments/assets/f7164d7a-5a91-40a9-ae14-45a5af5ffa82)

```c
df.boxplot(column="Age",by="Survived")
```
![image](https://github.com/user-attachments/assets/fcb87124-8610-43e0-ba89-a5bf83a1295e)

```c
sns.scatterplot(x=df["Age"],y=df["Fare"])
```
![image](https://github.com/user-attachments/assets/2dbab6dc-536e-42bd-93bd-5c9ac604ac3e)
```c
sns.jointplot(x="Age",y="Fare",data=df)
```
![image](https://github.com/user-attachments/assets/5b039429-4824-415e-b082-9d9873e575bf)
```c
fig, ax1 = plt.subplots(figsize=(8,5))
plt = sns.boxplot(ax=ax1,x='Pclass',y='Age',hue='Gender',data=df)
```
![image](https://github.com/user-attachments/assets/a7bc5cd4-c35d-40b0-bdfe-37b78cc35374)
```c
sns.catplot(data=df,col="Survived",x="Gender",hue="Pclass",kind="count")
```
![image](https://github.com/user-attachments/assets/e53833a6-2138-43d8-876d-10dc3e85ac45)
```c
numeric_df =df.select_dtypes(include=['number'])
corr =numeric_df.corr()
sns.heatmap(corr,annot=True)
```
![image](https://github.com/user-attachments/assets/fd3919f9-76b1-4ea8-af15-ed00a27bd38a)

```c
sns.pairplot(df)
```
![image](https://github.com/user-attachments/assets/00f66888-4423-411e-8657-6ef16fc7a16e)

# RESULT
Thus, To perform Exploratory Data Analysis on the given data set is implemented successfully.
