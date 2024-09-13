### Developed by : PRAVEEN S
### Register No.: 212222240078
### Date :

# Ex.No: 03   COMPUTE THE AUTO FUNCTION(ACF)

### AIM:
To Compute the AutoCorrelation Function (ACF) of the data for The Minimum Price of the Onion.

### ALGORITHM:

1. Import the necessary packages

2. Find the mean, variance and then implement normalization for the data.

3. Implement the correlation using necessary logic and obtain the results

4. Store the results in an array

5. Represent the result in graphical representation as given below.

### PROGRAM:

```py
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt

file_path = '/content/OnionTimeSeries - Sheet1.csv'
data = pd.read_csv(file_path)

Min_data = data['Min'].dropna().values

data_mean = np.mean(Min_data)
print("Mean:", data_mean)

data_var = np.var(Min_data)
print("Variance:", data_var)

normalized_data = (Min_data - data_mean) / np.sqrt(data_var)

acf_result = np.correlate(normalized_data, normalized_data, mode='full')

acf_result = acf_result[len(acf_result)//2:]

plt.figure(figsize=(10, 5))
plt.stem(acf_result[:36], use_line_collection=True)
plt.xlabel('Lag')
plt.ylabel('Autocorrelation')
plt.title('Autocorrelation Function (ACF) of Minimum Price of Onion')
plt.show()

```
### OUTPUT:

![image](https://github.com/user-attachments/assets/131277ff-6927-4aa8-b8d2-d2207b4f8211)


#### Autocorrelation Function (ACF) of Minimum Price of Onion

![Untitled](https://github.com/user-attachments/assets/aa8e9bda-df98-4e0c-9cff-2871baaa13e9)



### RESULT:

####     Thus auto correlation function in python is successfully implemented.
