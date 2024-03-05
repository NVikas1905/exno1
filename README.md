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
    import pandas as pd
    df=pd.read_csv("/content/Data_set .csv")
    df
    df.head(10)
    df.info()
    df.isnull()
    df.isnull().sum()
    df['show_name']=df['show_name'].fillna(df['aired_on'].mode()[0])
    df['aired_on']=df['aired_on'].fillna(df['aired_on'].mode()[0])
    df['original_network']=df['original_network'].fillna(df['aired_on'].mode()[0])
    df.head()
    df['rating']=df['rating'].fillna(df['rating'].mean())
    df['current_overall_rank']=df['current_overall_rank'].fillna(df['current_overall_rank'].mean
    df.head()
    df['watchers']=df['watchers'].fillna(df['watchers'].median())
    df.head()
    df.info()
    df.isnull().sum()
# Result
![307779755-b581b6e4-b8b3-481f-a93c-3ff7421c1a0c](https://github.com/NVikas1905/exno1/assets/133752491/1bb2c4b4-4a28-4802-af7b-c43285bf1094)
![307779800-cb40ed94-b364-4e1f-8d5b-293f5c1d39cf](https://github.com/NVikas1905/exno1/assets/133752491/e74d930d-45c3-4ddd-a978-7041a68cd5e8)
![307779853-850fbe7a-a9a6-4fac-ac8a-83b7a619c0ba](https://github.com/NVikas1905/exno1/assets/133752491/76eb0cdf-8b71-46f0-9752-534195ad76c7)
![307779905-d9317b7b-5f04-4682-a175-4fe61f361f0a](https://github.com/NVikas1905/exno1/assets/133752491/ac7fcee7-e75f-4654-be44-f2487f38e139)
![307779936-a4928c49-2918-49b6-9e77-8d17ed8da2dd](https://github.com/NVikas1905/exno1/assets/133752491/2043f1e7-fd6f-4e2e-993a-764df7eb74db)
![307780043-02b1b7f7-d360-4217-8bad-71ed011fde5f](https://github.com/NVikas1905/exno1/assets/133752491/da1027d7-68bd-443c-aa9f-374c44fe020f)
![307780074-c73f02d8-64e5-47ca-ba0a-0de5c4e63747](https://github.com/NVikas1905/exno1/assets/133752491/c4fea6d4-9cb3-47ca-a17c-44fbdc4115c1)
![307780107-3fb85203-8458-445a-9e13-3b9f42c0c82c](https://github.com/NVikas1905/exno1/assets/133752491/77104dec-a4e4-40a5-aba1-6128f498bf2d)
![307780185-2edc3c80-074e-4b73-aa25-fef19d23f799](https://github.com/NVikas1905/exno1/assets/133752491/c581d5dc-c0e6-4d4b-8c24-cc7ae7c9ea06)
![307780332-d2e49792-c9a3-4b2b-87c2-6031e07fe18b](https://github.com/NVikas1905/exno1/assets/133752491/04abc817-c20a-4805-9047-994d831f8a01)
![307780539-6fab031c-16da-41e8-b152-f3900b258460](https://github.com/NVikas1905/exno1/assets/133752491/a3a9fedb-5394-410b-baa7-c9e371bb79a9)
![307780663-590becd6-d7bb-4f05-9eed-6a1ebc296379](https://github.com/NVikas1905/exno1/assets/133752491/faddd1c6-c755-460a-91a0-971c00970665)
![307780705-81626ddf-2bf6-45f4-8869-8621be32a9f8](https://github.com/NVikas1905/exno1/assets/133752491/7e979fee-2726-4769-85f3-4d5fc0b5c567)
![307781168-0f292fcc-4a18-4a7b-a5e2-a26dd71a53ea](https://github.com/NVikas1905/exno1/assets/133752491/8bf4467f-40eb-4f38-839a-46b91e882827)
![307781248-3ca75707-984a-46f9-93a0-86ed7eb9cd8d](https://github.com/NVikas1905/exno1/assets/133752491/ce7c7bb9-a558-43dd-9764-7d6ef5a7cde6)
![307781315-ecc2bfd7-2b85-4299-9f6e-540627fe4744](https://github.com/NVikas1905/exno1/assets/133752491/11c5dc33-028e-47fd-8444-b8139c35b0f1)
![307781373-c2891cdd-b5d1-435a-8a2a-14416a08795d](https://github.com/NVikas1905/exno1/assets/133752491/3e2460b2-dd85-45e6-9946-844b2fecce78)


# 2)Outlier Detection and Removal

# AIM:
To read a given dataset and remove outliers and save a new dataframe.

# ALGORITHM:

(1) Remove outliers using IQR

(2) After removing outliers in step 1, you get a new dataframe.

(3) use zscore of 3 to remove outliers. This is quite similar to IQR and you will get exact same result

(4) for the data set height_weight.csv find the following

(i) Using IQR detect weight outliers and print them

(ii) Using IQR, detect height outliers and print them

# PROGRAM

    import pandas as pd
    import numpy as np
    import seaborn as sns
    import pandas as pd
    from scipy import stats
    df = pd.read_csv("/content/heights.csv")
    sns.boxplot(data=df)
    sns.scatterplot(data=df)
    max =df['height'].quantile(0.90)
    min =df['height'].quantile(0.15)
    max
    min
    dq = df[((df['height']>=min)&(df['height']<=max))]
    dq
    low = min-1.5*iqr
    high = max+1.5*iqr
    dq = df[((df['height']>=min)&(df['height']<=max))]
    dq


# ZSCORE:

    import pandas as pd
    import numpy as np
    import seaborn as sns
    import pandas as pd
    from scipy import stats
    data = {'weight':[12,15,18,21,24,27,30,33,36,39,42,45,48,51,54,57,60,63,66,69,202,72,75,78,81,84,232,87,90,93,96,99,258]}
    df = pd.DataFrame(data)
    df
    sns.boxplot(data=df)
    z = np.abs(stats.zscore(df))
    print(df[z['weight']>3])
    val =[12,15,18,21,24,27,30,33,36,39,42,45,48,51,54,57,60,63,66,69,202,72,75,78,81,84,232,87,90,93,96,99,258]
    out=[]
    def d_o(val):
    ts=3
    m=np.mean(val)
    sd=np.std(val)    
    for i in val:
    z=(i-m)/sd
    if np.abs(z)>ts:
    out.append(i)
    return out
    op = d_o(val)
    op


# OUTPUT
![307783134-2f1a046f-49e9-440a-ba5f-8c16dae0e97d](https://github.com/NVikas1905/exno1/assets/133752491/e59cce11-a9a4-42ad-8f66-61a57c71be8b)
![307783152-9180b739-53e6-4d08-9761-eb41d79089ea](https://github.com/NVikas1905/exno1/assets/133752491/3591b2b5-ed4f-473e-be17-ce40ceead5c6)
![307783380-95daf9ae-454f-4924-ba58-b828b333e3b1](https://github.com/NVikas1905/exno1/assets/133752491/90d87060-87b0-45d1-82ca-55297a67e9c3)
![307783428-d889c5ca-07e3-4224-bc95-8a3e9faa1064](https://github.com/NVikas1905/exno1/assets/133752491/c4a60a28-0299-44c9-b67d-7030e4ae1416)
![307783469-55f97582-795b-4864-aacf-f8df9fc3bea9](https://github.com/NVikas1905/exno1/assets/133752491/e23d7d25-399e-4d85-aa06-0d2845e7dbc2)
![307783511-5d50f766-e253-4177-a6b0-bcfba5e14a17](https://github.com/NVikas1905/exno1/assets/133752491/c3df9882-3554-4f48-88f4-65fd7f06b5dc)


# RESULT

Thus, the given data is read, cleansed and the cleaned data is saved into the file and the given data is read,remove outliers and save a new dataframe was created and executed successfully.


