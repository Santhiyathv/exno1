NAME:SANTHIYA B
#REGISTER NUMBER:212224230247
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
          import numpy as np
          import seaborn as sns
          import os 
          df=pd.read_csv("SAMPLEIDS.csv")
          df
```
          ![image](https://github.com/user-attachments/assets/2cd1104e-20e3-4058-a31c-32f738c54ca4)
        ```  df.isnull().sum() ```
          ![image](https://github.com/user-attachments/assets/9630ab0e-065f-4023-b12b-a41d49e8b8a6)
          df.isnull().any()
          ![image](https://github.com/user-attachments/assets/a0400585-6fcd-4d89-b971-691a8d7e079d)
          df.dropna()
          ![image](https://github.com/user-attachments/assets/e381e160-3b50-40ca-914f-9f06169d4e8d)
          df.fillna(0)
          ![image](https://github.com/user-attachments/assets/78c27c1d-f992-4a3e-81a1-53c976953cfe)
          df.fillna(method = 'ffill')
          ![image](https://github.com/user-attachments/assets/fe20614b-a09b-419e-8722-81e85dbfdac5)
          df.fillna(method = 'bfill')
         ![image](https://github.com/user-attachments/assets/6b3a4975-0484-420d-b168-7013d13b62fb)
         df_dropped = df.dropna()
           df_dropped
          ![image](https://github.com/user-attachments/assets/aa41cf3a-33b3-444b-bb34-38e2aa0d24f0)
        df.fillna({'GENDER':'MALE','NAME':'KANISHKAR','ADDRESS':'POONAMALEE','M1':98,'M2':87,'M3':76,'M4':92,'TOTAL':305,'AVG':89.999999})
        ![image](https://github.com/user-attachments/assets/68068df8-11b9-4db2-8313-d46bf5bbcdf4)
                 import pandas as pd
         
         ir=pd.read_csv('iris.csv')
         ir
         ![image](https://github.com/user-attachments/assets/2be72c11-60fd-4ddf-a480-bc40756d6b94)
                  ir.describe()
         ![image](https://github.com/user-attachments/assets/0d96aa40-2214-462f-b636-4439e80e5407)
                  import seaborn as sns
         
         sns.boxplot(x='sepal_width',data=ir)
         ![image](https://github.com/user-attachments/assets/94f6cc9c-9fad-4132-9ef6-34b740d35cb0)
                    c1=ir.sepal_width.quantile(0.25)
           c3=ir.sepal_width.quantile(0.75)
           iq=c3-c1
           print(c3)
           3.3
                       rid=ir[((ir.sepal_width<(c1-1.5*iq))|(ir.sepal_width>(c3+1.5*iq)))]
            rid['sepal_width']
            ![image](https://github.com/user-attachments/assets/c07384b5-a6cc-4a17-934f-9bb51731084e)
                        delid=ir[~((ir.sepal_width<(c1-1.5*iq))|(ir.sepal_width>(c3+1.5*iq)))]
            delid
            ![image](https://github.com/user-attachments/assets/742c3322-3a83-4eda-ad41-ed7bd4a51baf)
                       sns.boxplot(x='sepal_width',data=delid)
            ![image](https://github.com/user-attachments/assets/438427ca-a537-43d9-9184-baa1b3bd3c0c)
                        import matplotlib.pyplot as plt
            import pandas as pd
            import numpy as np
            import scipy.stats as stats

            dataset=pd.read_csv("heights.csv")
            dataset
            ![image](https://github.com/user-attachments/assets/a17293e5-a27b-47eb-8009-08e8471ad59b)
                        df = pd.read_csv("heights.csv")
            q1 = df['height'].quantile(0.25)
            q2 = df['height'].quantile(0.5)
            q3 = df['height'].quantile(0.75)
            
            iqr = q3-q1
            iqr
            ![image](https://github.com/user-attachments/assets/ce91ea9d-886e-45f2-9f2d-94772d25292a)
                    low = q1 - 1.5*iqr
        low
        ![image](https://github.com/user-attachments/assets/d87d25c0-815e-4155-9047-7089852dad4a)
                high = q3 + 1.5*iqr
        high
        ![image](https://github.com/user-attachments/assets/e1a58d1a-39b3-4dec-aea1-52928f2644f2)
                df1 = df[((df['height'] >=low)& (df['height'] <=high))]
        df1
        ![image](https://github.com/user-attachments/assets/d5543f63-15ef-4685-90fb-8dd9379b549d)
                z = np.abs(stats.zscore(df['height']))
        z
        ![image](https://github.com/user-attachments/assets/d1814947-3584-4be4-8dba-bd4aa26267dd)
                df1 = df[z<3]
        df1
        ![image](https://github.com/user-attachments/assets/2f03b7bd-f392-4584-a2d8-3de726b77365)


        




            
            


           






 







# Result
           Thus the given data successfully performed data cleaning and saved the cleaned data to a file.
