# Data-Science-Assignment-Lab-Introduction

# Activity
## 1. Write a Python program to select the 'name' and 'score' columns from the following DataFrame.

```py
Sample DataFrame:
       exam_data = {'name': ['Anastasia', 'Dima', 'Katherine', 'James', 
                             'Emily', 'Michael', 'Matthew', 'Laura', 'Kevin',
                             'Jonas'],
                    'score': [12.5, 9, 16.5, np.nan, 9, 20, 14.5, np.nan, 8, 19],
                    'attempts': [1, 3, 4, 3, 5, 3, 6, 1, 7, 1] } 
```

```py
import numpy as np
import pandas as pd

exam_data = {'name': ['Anastasia', 'Dima', 'Katherine', 'James', 'Emily', 'Michael', 'Matthew', 'Laura', 'Kevin', 'Jonas'],
             'score': [12.5, 9, 16.5, np.nan, 9, 20, 14.5, np.nan, 8, 19],
             'attempts': [1, 3, 4, 3, 5, 3, 6, 1, 7, 1] }
df = pd.DataFrame(exam_data)
df
```
![image](https://github.com/user-attachments/assets/9c5e8cd4-15c0-49d6-9fe5-5aebd59f9953)

---

## 2. For the above dataframe, Write a program to select the data who's attempt is greater than 3.

```py 
GreaterThanThree = df[df['attempts'] > 3]
GreaterThanThree
```
<br />

![image](https://github.com/user-attachments/assets/6fc190da-0fa7-4803-afcc-0ad435bb5a6a)

---

## 3. Write python code for indexing rows and columns based on the following conditions:

### Assume we have the following dataframe:

```py
data = {'name': ['Alice', 'Bob', 'Charlie', 'Dave'],
        'age': [25, 35, 40, 28],
        'gender': ['F', 'M', 'M', 'M'],
        'salary': [50000, 70000, 60000, 80000]
       }

df = pd.DataFrame(data)
```
```py
data = {'name': ['Alice', 'Bob', 'Charlie', 'Dave'],
        'age': [25, 35, 40, 28],
        'gender': ['F', 'M', 'M', 'M'],
        'salary': [50000, 70000, 60000, 80000]}

dp = pd.DataFrame(data)
dp
```

![image](https://github.com/user-attachments/assets/19259c64-5dbf-4b0b-8d61-a578e68603bc)

### a. Select rows where age is greater than 30:
```py
AgeGreaterThan30 = dp[dp['age'] > 30]
AgeGreaterThan30
```

![image](https://github.com/user-attachments/assets/87bac259-8987-4d5c-b34c-d354ce10fbbd)

### b. Select rows where name contains 'e':
```py
RowsContainingE = df[df['name'].str.contains('e')]
RowsContainingE
```

![image](https://github.com/user-attachments/assets/cb591782-5484-4f32-98eb-30c9da80d041)

### c. Select rows where gender is 'M' and salary is greater than 65000:
```py
GenderAndSalary = dp[(dp['gender'] == 'M') & (dp['salary'] > 65000)]
GenderAndSalary
```

![image](https://github.com/user-attachments/assets/4e9658ff-d088-42e9-9377-89ea6d7f8464)

### d. Select columns 'name' and 'age'
```py
NameAndAge = dp[['name','age']]
NameAndAge
```

![image](https://github.com/user-attachments/assets/454b5f3a-ce41-4eab-8e13-4abb88f216ab)

---
# ACTIVITY 2:
## 1. Write python code for indexing rows and columns using iloc or loc method based on the following conditions:
```py
from google.colab import drive
drive.mount('/content/drive')
ls 'drive/MyDrive/Colab Notebooks'
```

![image](https://github.com/user-attachments/assets/ebe9447a-934b-473b-a18c-6c6d45e06dea)

```py
df = pd.read_csv('drive/MyDrive/Colab Notebooks/bank_train.csv')
```

### a. select the rows where clients with primary education have subscribed to a deposit?
```py
PrimaryEducationDeposit = df.loc[(df['education'] == 'primary') & (df['deposit'] == 'yes')]
PrimaryEducationDeposit
```

![image](https://github.com/user-attachments/assets/f747c12f-beb7-4fd4-adfa-b555ddcc42e2)

### b. select the rows where clients who have not subscribed to a deposit?
```py
SubscribedToDeposit = df.loc[df['deposit'] == 'no']
SubscribedToDeposit
```

![image](https://github.com/user-attachments/assets/556373d5-e0b6-4cb1-8366-d18cae0251ce)

### c. select the rows where clients who have subscribed to a deposit either have a housing or a personal loan?
```py
DepositHousingLoan = df.loc[(df['deposit'] == 'yes') & ((df['housing'] == 'yes') | (df['loan'] == 'yes'))]
DepositHousingLoan
```

![image](https://github.com/user-attachments/assets/cc5c91a3-5102-4f9b-882d-b02f0426bf0e)

### d. select the rows where clients with secondary education who have not subscribed to a deposit?
```py
SecondayNoDeposit = df.loc[(df['education'] == 'secondary') & (df['deposit'] == 'no')]
SecondayNoDeposit
```

![image](https://github.com/user-attachments/assets/b63e0eeb-50ac-4560-9456-ebe397f731cd)

### e. select the rows where clients who have subscribed to a term deposit as an outcome of the successful marketing campaign?
```py
MarketCampain = df.loc[(df['poutcome'] == 'success') & (df['deposit'] == 'yes')]
MarketCampain
```

![image](https://github.com/user-attachments/assets/cefb3910-a93a-4ae1-85a3-a7c82aaf7c01)

### f. select the rows where unemployed clients who have not subscribed to deposit?
```py
UnemployedNoDeposit = df.loc[(df['job'] == 'unemployed') & (df['deposit'] == 'no')]
UnemployedNoDeposit
```

![image](https://github.com/user-attachments/assets/1faca5f4-fab7-4c2a-803b-c82ca243b2d4)

![image](https://github.com/user-attachments/assets/1eb22ceb-6c31-4ff1-b8b2-5460c65d59d4)

![image](https://github.com/user-attachments/assets/098eded3-ae17-457d-b080-b09552debccb)

![image](https://github.com/user-attachments/assets/9535f361-e113-44d7-99e7-0eed8e7c0155)

### g. Select columns 'name' and 'salary' where age is less than or equal to 30:
```py
NameSalary = dp.loc[dp['age'] < 30,['name','salary']]
NameSalary
```

![image](https://github.com/user-attachments/assets/24791336-fa26-4090-a45d-cd8617dc1f6f)
---
