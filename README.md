# Ex.No: 05  IMPLEMENTATION OF TIME SERIES ANALYSIS AND DECOMPOSITION
### Date: 


### AIM:
To Illustrates how to perform time series analysis and decomposition on the solar radiation from astrobiological activity monitoring.

### ALGORITHM:
1. Import the required packages like pandas and numpy
2. Read the data using the pandas
3. Perform the decomposition process for the required data.
4. Plot the data according to need, either seasonal_decomposition or trend plot.
5. Display the overall results.

### PROGRAM:
```
NAME:MANOJ G
REG_NO:212222240060
```
```
import pandas as pd
import matplotlib.pyplot as plt
from statsmodels.tsa.seasonal import seasonal_decompose

# Load the dataset
file_path = 'astrobiological_activity_monitoring.csv'
data = pd.read_csv(file_path)

# Convert 'Date' to datetime format and set it as the index
data['Date'] = pd.to_datetime(data['Date'])
data.set_index('Date', inplace=True)

# Perform time series decomposition on 'Solar_Radiation' using additive model
series = data['Solar_Radiation']
decomposition = seasonal_decompose(series, model='additive', period=30)  # Assuming monthly seasonality (30 days)

# Plot the decomposed components: observed, trend, seasonal, and residual
plt.figure(figsize=(12, 8))

plt.subplot(411)
plt.plot(decomposition.observed, label='Observed')
plt.legend(loc='upper left')

plt.subplot(412)
plt.plot(decomposition.trend, label='Trend', color='orange')
plt.legend(loc='upper left')

plt.subplot(413)
plt.plot(decomposition.seasonal, label='Seasonal', color='green')
plt.legend(loc='upper left')

plt.subplot(414)
plt.plot(decomposition.resid, label='Residual', color='red')
plt.legend(loc='upper left')

plt.tight_layout()
plt.show()

```


### OUTPUT:
![image](https://github.com/user-attachments/assets/1b6dd619-e6be-4922-b7cb-755617a4d638)





### RESULT:
Thus we have created the python code for the time series analysis and decomposition.





### RESULT:
Thus the python code for the time series analysis and decomposition is created and executed successfully.
