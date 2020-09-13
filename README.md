# Machine-learning-with-Python

In order to predict the geometrical and dimensional quality charactersictics such as diameter and concentricity of machined workpieces, Supervised Machine Learning methods such as 
Random Forest, Artificial Neural Network (ANN) etc.. were implemented.

![Architecture of the system](https://github.com/a-mujumdar/Machine-learning-with-Python/blob/master/Plots/architecture.PNG)

## Data acquisition

The raw time series data (process data) were obtained from milling-machine in the serial production of hydraulic valves. Through the Numerical Controllers (NC), an increasing 
amount of process data for each workpiece is available. Torque values from the drives of the spindle were gathered for this use case.

## Feature extraction and selection

In order to obtain relevant information for the quality prediction and to reduce the amount of raw data to enable processing close to real time, determination of 
features is recommended. I extracted time-domain features such as mean, standard deviation, skewness, kurtosis etc.. and frequency domain features such as mean power, 
peak magnitude from FFT (Fast Fourier Transform) spectrum and spectral features such as mean band power, variance of band power using Power Spectral Density (PSD) by Welch method.

Feature selection was performed using Pearson correlation coefficient and Recursive Feature Elimination Support Vector Machine (RFE-SVM), where only significant (top ranked 
or highly correlated features) were selected and given as input to the Machine Learning models for **Regression**.
