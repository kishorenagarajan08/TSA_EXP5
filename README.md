# Ex.No: 05  IMPLEMENTATION OF TIME SERIES ANALYSIS AND DECOMPOSITION
### Date: 4/10/2025
### Name:Kishore N



### AIM:
To Illustrates how to perform time series analysis and decomposition on the monthly average temperature of a city/country and for airline passengers.

### ALGORITHM:
1. Import the required packages like pandas and numpy
2. Read the data using the pandas
3. Perform the decomposition process for the required data.
4. Plot the data according to need, either seasonal_decomposition or trend plot.
5. Display the overall results.

### PROGRAM:
Import necessary libraries:
```
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
from statsmodels.tsa.seasonal import seasonal_decompose
```
Load the dataset:
```
data = pd.read_csv('GoogleStockPrices.csv', parse_dates=['Date'], index_col='Date')
print("Columns in dataset:", data.columns)
X = data['Close']
```
Perform seasonal decomposition:
```
decomposition = seasonal_decompose(X, model='multiplicative', period=252)
```
Plot the decomposition:
```
plt.figure(figsize=(10, 12))
```
Original Data:
```
plt.subplot(411)
plt.plot(X, label='Google Stock Closing Price')
plt.legend(loc='upper left')
plt.title('Google Stock Price (Close)')
```
Trend Plot:
```
plt.subplot(412)
plt.plot(decomposition.trend, label='Trend', color='orange')
plt.legend(loc='upper left')
plt.title('Trend Plot')
```
Seasonal Plot:
```
plt.subplot(413)
plt.plot(decomposition.seasonal, label='Seasonal', color='green')
plt.legend(loc='upper left')
plt.title('Seasonality Plot')
```
Residual Plot:
```
plt.subplot(414)
plt.plot(decomposition.resid, label='Residual', color='red')
plt.legend(loc='upper left')
plt.title('Residual Plot')

plt.tight_layout()
plt.show()
```

### OUTPUT:

Original Time series data:

<img width="983" height="280" alt="image" src="https://github.com/user-attachments/assets/40e2c161-c92a-40b1-99d3-f0bfff55ccc9" />

Linear Trend plot:

<img width="980" height="279" alt="image" src="https://github.com/user-attachments/assets/9cb1024c-9eeb-4f44-a75d-23003a15d2a1" />

Seasonality plot:

<img width="984" height="278" alt="image" src="https://github.com/user-attachments/assets/83810544-0394-4b0f-8e23-11098e96294a" />

Residual plot:

<img width="987" height="301" alt="image" src="https://github.com/user-attachments/assets/e25e5015-0796-4258-a3c3-f65322610742" />

### RESULT:
Thus we have created the python code for the time series analysis and decomposition.
