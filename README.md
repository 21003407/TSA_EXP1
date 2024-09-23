# NAME: A joans jay authers 
# REG.NO: 212221240019
# DATE:
# Ex.No: 01A PLOT A TIME SERIES DATA


# AIM:
To Develop a python program to Plot a time series data (cinema ticket)
# ALGORITHM:

1.Load the necessary libraries for data manipulation and visualization.

2.Read the data from the CSV file into a DataFrame.

3.Change the 'date' column to datetime format for time series analysis.

4.Aggregate the total sales data by month and compute the average.

5.Aggregate the total sales data by year and compute the average.

6.Set up the plot with the desired figure size.

7.Plot the monthly average sales data with a line graph and label it.

8.Include axis labels, a title, and a legend for clarity.

9.Show the plot to visualize the results.

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







# RESULT
Thus a time series plot of the cinema tickets data is successfully generated, visualizing monthly sold tickets with approiate labels, title, gridlines
