# NAME: AMURTHA VAAHINI.KN
# REG.NO: 212222240008
# DATE:
# Ex.No: 01A PLOT A TIME SERIES DATA


# AIM:
To Develop a python program to Plot a time series data (population/ market price of a commodity
/temperature.
# ALGORITHM:
1. Import the required packages like pandas and matplot
2. Read the dataset using the pandas
3. Calculate the mean for the respective column.
4. Plot the data according to need and can be altered monthly, or yearly.
5. Display the graph.
# PROGRAM
```
import pandas as pd
import matplotlib.pyplot as plt
df = pd.read_csv('cinemaTicket_Ref.csv')
df['date'] = pd.to_datetime(df['date'])
monthly_mean = df['total_sales'].resample('M').mean()
yearly_mean = df['total_sales'].resample('Y').mean()
plt.figure(figsize=(12, 6))
plt.plot(monthly_mean, label='Monthly Mean of Tickets Sold', color='blue')
```

# OUTPUT:
![image](https://github.com/user-attachments/assets/7d1a5b47-fcc1-465e-bd26-1ca2951cb3df)







# RESULT:
Thus we have created the python code for plotting the time series of given data.
