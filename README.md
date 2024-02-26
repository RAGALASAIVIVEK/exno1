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
```
import pandas as pd
df=pd.read_csv("/content/SAMPLEIDS.csv")
df
```
![image](https://github.com/RAGALASAIVIVEK/exno1/assets/144979718/0e23120c-2534-4e35-a3cb-05d5b85fcb73)
```
print(df.head(7))
```
![image](https://github.com/RAGALASAIVIVEK/exno1/assets/144979718/6fad3c6e-cc37-466f-9918-e4475288ead2)
```
print(df.tail(2))
```
![image](https://github.com/RAGALASAIVIVEK/exno1/assets/144979718/e3c6d1a5-087a-47c4-8272-4be05fdbe004)
```
df.info()
```
![image](https://github.com/RAGALASAIVIVEK/exno1/assets/144979718/9a3cb053-8aa4-4283-9500-dd1204b480b8)
```
print(df.describe())
```
![image](https://github.com/RAGALASAIVIVEK/exno1/assets/144979718/4cdb32fa-8f22-4362-81fc-a386eb348c09)
```
df.isnull().sum()
```
![image](https://github.com/RAGALASAIVIVEK/exno1/assets/144979718/1c11a081-40c7-4eab-bc2c-c2e8fd914bd9)
```
df.nunique()
```
![image](https://github.com/RAGALASAIVIVEK/exno1/assets/144979718/0b20e6c3-d3ff-4456-a39f-224e0ed446a5)
```
mn=df.TOTAL.mean()
mn
```
![image](https://github.com/RAGALASAIVIVEK/exno1/assets/144979718/391dc54c-935d-4797-b004-e7e19b35731c)

```
df.TOTAL.fillna(mn,inplace=True)
df
```
![image](https://github.com/RAGALASAIVIVEK/exno1/assets/144979718/d38d8d7b-d078-41be-94b8-2a5bb83e1ea4)
```
min=df.M4.min()
min
```
![image](https://github.com/RAGALASAIVIVEK/exno1/assets/144979718/2a478e8c-588b-432f-b6e7-f85c02a0e4ba)
```
df.M4.fillna(min,inplace=True)
df
```
![image](https://github.com/RAGALASAIVIVEK/exno1/assets/144979718/9c4bb18f-9ba8-4316-ac83-049ac9d9c601)

![image](https://github.com/RAGALASAIVIVEK/exno1/assets/144979718/50729ba2-6975-4967-a550-a73951a484b1)
```
import pandas as pd
import seaborn as sns
age=[1,3,28,27,25,92,30,39,40,50,26,24,29,94]
af=pd.DataFrame(age)
af
```
![op1](https://github.com/RAGALASAIVIVEK/exno1/assets/144979718/3b9da63d-2ea1-44e5-af38-4bd2bcaf4725)
```
sns.boxplot(data=af)
```
![op2](https://github.com/RAGALASAIVIVEK/exno1/assets/144979718/ae99341a-1b57-43bf-a10d-c590430ac5dc)

```
sns.scatterplot(data=af)
```
![op3](https://github.com/RAGALASAIVIVEK/exno1/assets/144979718/f4891641-c25c-4195-a62e-381f25de97ec)
```
q1=af.quantile(0.25)
q2=af.quantile(0.50)
q3=af.quantile(0.75)
iqr=q3-q1
iqr
low=q1-1.5*iqr
low
high=q3+1.5*iqr
high
```
![op4](https://github.com/RAGALASAIVIVEK/exno1/assets/144979718/43a48ae5-a004-4413-af27-b0996bd82853)
```
af=af[((af>=low)&(af<=high))]
af
```
![op5](https://github.com/RAGALASAIVIVEK/exno1/assets/144979718/f3a4b482-2aeb-4506-8c1b-a1a383f33826)

```
af.dropna()
```
![op6](https://github.com/RAGALASAIVIVEK/exno1/assets/144979718/662830a1-0c56-4853-bcfe-eb8ae9b2b6e6)
```
sns.boxplot(data=af)
```
![op7](https://github.com/RAGALASAIVIVEK/exno1/assets/144979718/56f6f964-a6b5-4137-ae05-3ca97bc4b49f)

```
sns.scatterplot(data=af)
```
![op8](https://github.com/RAGALASAIVIVEK/exno1/assets/144979718/e44c0cba-2e84-493e-ab26-6a970697a743)
```
data=[1,12,15,18,21,24,27,30,33,36,39,42,45,48,51,54,57,60,63,66,69,72,75,78,81,84,87,90,93,96,99,102,105]
df=pd.DataFrame(data)
df
```
![op9](https://github.com/RAGALASAIVIVEK/exno1/assets/144979718/38a6a707-b591-4ab7-8434-11d3346f8f9f)
```
import numpy as np
from scipy import stats
z=np.abs(stats.zscore(df))
z
```
![op10](https://github.com/RAGALASAIVIVEK/exno1/assets/144979718/76984ab4-8e15-478d-b6dd-5861affa15f8)

# Result
Thus the given program executed successfully.
