# EXNO:4-DS
# AIM:
To read the given data and perform Feature Scaling and Feature Selection process and save the
data to a file.

# ALGORITHM:
STEP 1:Read the given Data.
STEP 2:Clean the Data Set using Data Cleaning Process.
STEP 3:Apply Feature Scaling for the feature in the data set.
STEP 4:Apply Feature Selection for the feature in the data set.
STEP 5:Save the data to the file.

# FEATURE SCALING:
1. Standard Scaler: It is also called Z-score normalization. It calculates the z-score of each value and replaces the value with the calculated Z-score. The features are then rescaled with x̄ =0 and σ=1
2. MinMaxScaler: It is also referred to as Normalization. The features are scaled between 0 and 1. Here, the mean value remains same as in Standardization, that is,0.
3. Maximum absolute scaling: Maximum absolute scaling scales the data to its maximum value; that is,it divides every observation by the maximum value of the variable.The result of the preceding transformation is a distribution in which the values vary approximately within the range of -1 to 1.
4. RobustScaler: RobustScaler transforms the feature vector by subtracting the median and then dividing by the interquartile range (75% value — 25% value).

# FEATURE SELECTION:
Feature selection is to find the best set of features that allows one to build useful models. Selecting the best features helps the model to perform well.
The feature selection techniques used are:
1.Filter Method
2.Wrapper Method
3.Embedded Method

# CODING AND OUTPUT:
```
import pandas as pd
from scipy import stats
import numpy as np
df=pd.read_csv("/content/bmi (1).csv")
df.head()
```
![4 1](https://github.com/user-attachments/assets/327f8406-8f82-4b9a-8a39-12f6ba3fc9d9)

```
df.tail()
```
![4 2](https://github.com/user-attachments/assets/10e187b6-a826-48d8-93d3-150ae773974c)

```
df.info()
```
![4 3](https://github.com/user-attachments/assets/a0f3f61e-e8f8-4774-a03e-ac131a810898)

```
df.describe()
```
![4 4](https://github.com/user-attachments/assets/d2648be0-781b-432e-aa1f-6cb2265554a2)

```
df.dropna()
```
![4 5](https://github.com/user-attachments/assets/a8fd3ce4-ebd9-42eb-a687-584ac797dc27)

```
max_vals=np.max(np.abs(df[['Height','Weight']]))
max_vals
```
![4 6](https://github.com/user-attachments/assets/210a4386-87d5-4ebe-bfa3-9873cda19065)

```
from sklearn.preprocessing import StandardScaler
scaler=StandardScaler()
df1=df.copy()
df1[['Height','Weight']]=scaler.fit_transform(df[['Height','Weight']])
df1.head()
```
![4 7](https://github.com/user-attachments/assets/3de8fe3b-a234-4a87-aacb-afdfc033780e)

```
from sklearn.preprocessing import MinMaxScaler
scaler=MinMaxScaler()
df2=df.copy()
df2[['Height','Weight']]=scaler.fit_transform(df[['Height','Weight']])
df2.head()
```
![4 8](https://github.com/user-attachments/assets/371e38a0-03f2-4860-88a5-7e004923250c)

```
from sklearn.preprocessing import Normalizer
scaler=Normalizer()
df3=df.copy()
df3[['Height','Weight']]=scaler.fit_transform(df[['Height','Weight']])
df3.head()
```
![4 9](https://github.com/user-attachments/assets/b98f0f4f-942b-4d2d-adc6-66c8430c4823)

```
from sklearn.preprocessing import MaxAbsScaler
scaler=MaxAbsScaler()
df4=df.copy()
df4[['Height','Weight']]=scaler.fit_transform(df[['Height','Weight']])
df4.head()
```
![4 10](https://github.com/user-attachments/assets/2cea61f0-a59b-431a-9a72-e48f51447091)

```
from sklearn.preprocessing import RobustScaler
scaler=RobustScaler()
df5=df.copy()
df5[['Height','Weight']]=scaler.fit_transform(df[['Height','Weight']])
df5.head()
```
![4 11](https://github.com/user-attachments/assets/d3175474-95fc-43b6-a5cd-600f6c844548)


# RESULT:
Thus the given data has been read and  Feature Scaling and Feature Selection process are done.
