
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
import pandas as pd

df=pd.read_csv(r"C:\Users\DEEPIKA\Downloads\titanic_dataset.csv")

df

<img width="1310" height="504" alt="image" src="https://github.com/user-attachments/assets/045e1b24-fc85-4e5c-b40f-07868452923c" />

df.shape

<img width="1209" height="33" alt="image" src="https://github.com/user-attachments/assets/38aa6b5c-7662-4c57-86c8-a1145471ceb7" />

df.set_index("PassengerId",inplace=True)

df

<img width="1351" height="542" alt="image" src="https://github.com/user-attachments/assets/53bcbb56-04c3-4b09-947f-a112b81b676e" />

df.nunique

<img width="1115" height="829" alt="image" src="https://github.com/user-attachments/assets/71f538f0-de7f-4f83-b931-ad854ccdee35" />

df['Sex'].value_counts()

<img width="1225" height="87" alt="image" src="https://github.com/user-attachments/assets/57df803a-d65b-42e0-b4b2-fa1e6fafffa9" />

df.Survived.unique()

<img width="1209" height="43" alt="image" src="https://github.com/user-attachments/assets/56f1e8a6-c07e-4682-a7c4-3c15c09bb6b2" />

df.rename(columns={"Sex":"Gender"},inplace=True)

df

<img width="1326" height="515" alt="image" src="https://github.com/user-attachments/assets/ac10ef9c-d812-488d-972b-367a2ee71352" />

import seaborn as sns

sns.countplot(data=df)

<img width="1108" height="588" alt="image" src="https://github.com/user-attachments/assets/13624b9e-4ae3-4dbd-8579-bc03622b54da" />

sns.countplot(x="Survived",hue="Gender",data=df)

<img width="1110" height="572" alt="image" src="https://github.com/user-attachments/assets/5dc2f951-198a-4662-aa1a-47ca2d83d37d" />

sns.catplot(x="Survived",hue="Gender",data=df,kind="count")

<img width="1131" height="643" alt="image" src="https://github.com/user-attachments/assets/0d306706-0dfe-408d-991f-e1c5cafc4209" />

sns.catplot(x="Survived",hue="Gender",data=df,kind="violin")

<img width="1132" height="637" alt="image" src="https://github.com/user-attachments/assets/a968f7b1-0872-4967-bce5-09191f074a6a" />

sns.boxplot(data=df)

<img width="1264" height="549" alt="image" src="https://github.com/user-attachments/assets/265d9e9a-dcb6-43ae-bec3-c90117c18b8c" />

df.boxplot(column="Survived",by="Gender")

<img width="1275" height="594" alt="image" src="https://github.com/user-attachments/assets/58c9b7ff-7697-4e3e-b341-860aa73fe09a" />

sns.scatterplot(data=df)

<img width="962" height="545" alt="image" src="https://github.com/user-attachments/assets/d3420b5f-ffdb-4b73-a624-fe9c02f2e05b" />

sns.scatterplot(x=df['Age'],y=df['Fare'])

<img width="1267" height="552" alt="image" src="https://github.com/user-attachments/assets/c6c27097-56d2-49b7-8e5f-c958c6345de1" />

sns.jointplot(x='Age',y='Fare',data=df)

<img width="1256" height="763" alt="image" src="https://github.com/user-attachments/assets/b13e42e9-52ff-42e1-ad97-a5664918bac7" />

sns.jointplot(x='Age',y='Fare',data=df,kind="kde")

<img width="1279" height="762" alt="image" src="https://github.com/user-attachments/assets/b51d1fbf-71ca-4aee-93f5-ef24a32e59ce" />

sns.jointplot(x='Age',y='Fare',data=df,kind="hist")

<img width="1030" height="759" alt="image" src="https://github.com/user-attachments/assets/81bdc287-1184-42f8-bc67-df3c85ab1604" />

sns.catplot(x='Gender',col='Survived',data=df,kind='count',color='green')

<img width="1298" height="644" alt="image" src="https://github.com/user-attachments/assets/bdd30562-d4c3-40d4-b186-23c67617c542" />

sns.pairplot(data=df)

<img width="901" height="927" alt="image" src="https://github.com/user-attachments/assets/983749d4-439e-4dc3-afc5-0609bb539f01" />

corr1=df.select_dtypes(include=["number"]).corr()

sns.heatmap(corr1,annot=True)

<img width="1066" height="632" alt="image" src="https://github.com/user-attachments/assets/ba3d063d-1629-4092-b03c-1e3fbf42ab95" />

sns.catplot(x='Gender',col='Survived',data=df,kind='count',hue="Pclass")

<img width="1353" height="640" alt="image" src="https://github.com/user-attachments/assets/5c4edd02-55d4-4932-ad96-5a451411b4c7" />

import matplotlib.pyplot as plt

fig,ax1=plt.subplots(figsize=(8,5))

pt=sns.boxplot(ax=ax1,x='Pclass',y='Age',hue='Gender',data=df)

<img width="1159" height="558" alt="image" src="https://github.com/user-attachments/assets/f9cbb7fe-9233-4c0d-8f1b-6d6be28c918d" />
















# RESULT
Thus performing Exploratory Data Analysis on the given data set
