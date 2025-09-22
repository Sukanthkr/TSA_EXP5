# Ex.No: 05  IMPLEMENTATION OF TIME SERIES ANALYSIS AND DECOMPOSITION
### Date: 22.09.2025

### AIM:
To Illustrates how to perform time series analysis and decomposition on the monthly average temperature of a city/country and for airline passengers.

### ALGORITHM:
1. Import the required packages like pandas and numpy
2. Read the data using the pandas
3. Perform the decomposition process for the required data.
4. Plot the data according to need, either seasonal_decomposition or trend plot.
5. Display the overall results.

### PROGRAM:
```
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import statsmodels.api as sm
from statsmodels.tsa.seasonal import seasonal_decompose

data = sm.datasets.sunspots.load_pandas().data

data.head()

decomposition = seasonal_decompose(data['SUNACTIVITY'], model='additive',period=12)

plt.figure(figsize=(10, 12))
plt.subplot(411)
plt.plot(data['SUNACTIVITY'], label='Sun Activity')
plt.legend(loc='upper left')
plt.title('Sun Activity')

plt.subplot(412)
plt.plot(decomposition.trend, label='Trend', color='orange')
plt.legend(loc='upper left')
plt.title('Linear Trend Plot')

plt.subplot(413)
plt.plot(decomposition.seasonal, label='Seasonal', color='green')
plt.legend(loc='upper left')
plt.title('Seasonality Plot')

plt.subplot(414)
plt.plot(decomposition.resid, label='Residual', color='red')
plt.legend(loc='upper left')
plt.title('Residual Plot')
plt.tight_layout()
plt.show()

```
### OUTPUT:

PLOTTING THE DATA:
<img width="1225" height="368" alt="Screenshot 2025-09-22 152557" src="https://github.com/user-attachments/assets/2d0c3d93-0dfb-4904-9af4-ca14279cb509" />

SEASONAL PLOT REPRESENTATION :
<img width="1278" height="368" alt="Screenshot 2025-09-22 152838" src="https://github.com/user-attachments/assets/2baac112-a015-4db6-9fc1-e6339315fe1e" />

TREND PLOT REPRESENTATION :
<img width="1284" height="376" alt="Screenshot 2025-09-22 152906" src="https://github.com/user-attachments/assets/2e2602ec-b0a0-4ed9-ae2c-30602fa38aed" />

OVERALL REPRESENTATION:
<img width="1343" height="373" alt="Screenshot 2025-09-22 152949" src="https://github.com/user-attachments/assets/3918a00a-28b2-4f4d-9b4e-8b250f9053f4" />

### RESULT:
Thus we have created the python code for the time series analysis and decomposition.
