### Developed by: S LUBINDHER
### Register Number: 212222240056
### Date:
# Ex.No:04   FIT ARMA MODEL FOR TIME SERIES
 
### AIM:
To implement ARMA model in python.
### ALGORITHM:
1. Import necessary libraries.
2. Set up matplotlib settings for figure size.
3. Define an ARMA(1,1) process with coefficients ar1 and ma1, and generate a sample of 1000

data points using the ArmaProcess class. Plot the generated time series and set the title and x-
axis limits.

4. Display the autocorrelation and partial autocorrelation plots for the ARMA(1,1) process using
plot_acf and plot_pacf.
5. Define an ARMA(2,2) process with coefficients ar2 and ma2, and generate a sample of 10000

data points using the ArmaProcess class. Plot the generated time series and set the title and x-
axis limits.

6. Display the autocorrelation and partial autocorrelation plots for the ARMA(2,2) process using
plot_acf and plot_pacf.
### PROGRAM:
```
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
from statsmodels.tsa.arima_process import ArmaProcess
from statsmodels.graphics.tsaplots import plot_acf, plot_pacf
import warnings
warnings.filterwarnings('ignore')

# Load the dataset
data = pd.read_csv('NVIDIA_stock_price_Train.csv')

# Use the 'Close' price column
close_prices = data['Close'].dropna()

plt.rcParams['figure.figsize'] = [10, 7.5]

# Simulate ARMA(1,1) Process
ar1 = np.array([1, 0.33])
ma1 = np.array([1, 0.9])
ARMA_1 = ArmaProcess(ar1, ma1).generate_sample(nsample=len(close_prices))
plt.plot(ARMA_1)
plt.title('Simulated ARMA(1,1) Process')
plt.xlim([0, 200])
plt.show()

# Plot ACF and PACF for ARMA(1,1)
plot_acf(ARMA_1)
plot_pacf(ARMA_1)

# Simulate ARMA(2,2) Process
ar2 = np.array([1, 0.33, 0.5])
ma2 = np.array([1, 0.9, 0.3])
ARMA_2 = ArmaProcess(ar2, ma2).generate_sample(nsample=len(close_prices) * 10)
plt.plot(ARMA_2)
plt.title('Simulated ARMA(2,2) Process')
plt.xlim([0, 200])
plt.show()

# Plot ACF and PACF for ARMA(2,2)
plot_acf(ARMA_2)
plot_pacf(ARMA_2)
```

### OUTPUT:
![image](https://github.com/user-attachments/assets/b1d46d1f-9586-499c-83c7-157fe506d36a)
![image](https://github.com/user-attachments/assets/d77f5cf6-764d-4d81-b0bb-3d135661de8a)
![image](https://github.com/user-attachments/assets/8f5164b4-2d80-4875-985d-f8de56cffa80)
![image](https://github.com/user-attachments/assets/cece51d8-25f8-492b-8808-9e863997b40f)
![image](https://github.com/user-attachments/assets/5a463d66-8e80-4ccc-80e9-2890890e0964)

![image](https://github.com/user-attachments/assets/322a190f-556c-4abc-b76b-24450e096830)

### RESULT:
Thus, a python program is created to fit ARMA Model with "NVIDIA Stock price"  datasets successfully.
