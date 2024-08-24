# Ex.No: 01A PLOT A TIME SERIES DATA
###  Date: 23/08/2024

# AIM:
To Develop a python program to Plot a time series data (population/ market price of a commodity
/temperature.
# ALGORITHM:
1. Import the required packages like pandas and matplot
2. Read the dataset using the pandas
3. Calculate the mean for the respective column.
4. Plot the data according to need and can be altered monthly, or yearly.
5. Display the graph.
# PROGRAM:
```
import matplotlib.pyplot as plt
import pandas as pd
```

# Load the dataset
```
df = pd.read_csv("cinemaTicket_Ref.csv", parse_dates=["date"], index_col="date")
```

# Display the first few rows to understand the structure
```
print(df.head())
```
# Ensure no missing values in critical columns (e.g., total_sales, tickets_sold, ticket_price)
```
df.fillna(method='ffill', inplace=True)
```
# Resample the data by month and year
```
monthly_sales = df['total_sales'].resample('M').sum()
monthly_tickets_sold = df['tickets_sold'].resample('M').sum()
monthly_ticket_price = df['ticket_price'].resample('M').mean()
```

# Yearly Resampling
```
yearly_sales = df['total_sales'].resample('Y').sum()
yearly_tickets_sold = df['tickets_sold'].resample('Y').sum()
yearly_ticket_price = df['ticket_price'].resample('Y').mean()
```

# Plot Monthly Data
```
plt.figure(figsize=(10, 6))
plt.subplot(3, 1, 1)
monthly_sales.plot(kind='line', color='blue', label='Monthly Total Sales')
plt.title("Monthly Trends (Sales, Tickets Sold, Ticket Price)")
plt.ylabel("Total Sales")

plt.subplot(3, 1, 2)
monthly_tickets_sold.plot(kind='line', color='green', label='Monthly Tickets Sold')
plt.ylabel("Tickets Sold")

plt.subplot(3, 1, 3)
monthly_ticket_price.plot(kind='line', color='red', label='Monthly Ticket Price')
plt.ylabel("Ticket Price")
plt.xlabel("Month")
plt.tight_layout()
plt.show()
```
# Plot Yearly Data
```
plt.figure(figsize=(10, 6))
plt.subplot(3, 1, 1)
yearly_sales.plot(kind='line', color='blue', label='Yearly Total Sales')
plt.title("Yearly Trends (Sales, Tickets Sold, Ticket Price)")
plt.ylabel("Total Sales")

plt.subplot(3, 1, 2)
yearly_tickets_sold.plot(kind='line', color='green', label='Yearly Tickets Sold')
plt.ylabel("Tickets Sold")

plt.subplot(3, 1, 3)
yearly_ticket_price.plot(kind='line', color='red', label='Yearly Ticket Price')
plt.ylabel("Ticket Price")
plt.xlabel("Year")
plt.tight_layout()
plt.show()
```
# Additional Insights
```
print("Summary Statistics for Total Sales:")
print(df['total_sales'].describe())

print("Summary Statistics for Tickets Sold:")
print(df['tickets_sold'].describe())

print("Summary Statistics for Ticket Price:")
print(df['ticket_price'].describe())
```











# OUTPUT:
![image](https://github.com/user-attachments/assets/5c9486a6-237c-48c5-b5c6-9641459dbaa7)
![image](https://github.com/user-attachments/assets/7470b2ff-996c-4783-93c1-494122b6bbb6)






# RESULT:
Thus we have created the python code for plotting the time series of given data.
