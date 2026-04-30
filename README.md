# SGD-Regressor-for-Multivariate-Linear-Regression

## AIM:
To write a program to predict the price of the house and number of occupants in the house with SGD regressor.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. Data Preparation Load the dataset using pandas, clean column names, and separate input features (Size, Bedrooms) and target variables (Price, Occupants)
2. Data Scaling Apply feature scaling using StandardScaler to normalize the input data for better performance of the SGD model. 
3. Model Training Create two SGDRegressor models and train them using the scaled features to predict Price and Occupants.
4. Prediction Take user input, scale it using the same scaler, and use the trained models to predict house price and number of occupants.

## Program:
```
/*
Program to implement the multivariate linear regression model for predicting the price of the house and number of occupants in the house with SGD regressor.
Developed by: Naresh J
RegisterNumber:  212225230195
import pandas as pd
from sklearn.linear_model import SGDRegressor
from sklearn.preprocessing import StandardScaler

# Load dataset
data = pd.read_csv("house.csv")

# Remove unwanted spaces in column names
data.columns = data.columns.str.strip()

# Features (inputs)
X = data[['Size', 'Bedrooms']]

# Targets (outputs)
y_price = data['Price']
y_occ = data['Occupants']

# Scaling features
scaler = StandardScaler()
X_scaled = scaler.fit_transform(X)

# Create models
price_model = SGDRegressor(max_iter=1000, learning_rate='constant', eta0=0.01, random_state=42)
occ_model = SGDRegressor(max_iter=1000, learning_rate='constant', eta0=0.01, random_state=42)

# Train models
price_model.fit(X_scaled, y_price)
occ_model.fit(X_scaled, y_occ)

# User input
size = float(input("Enter house size: "))
bed = int(input("Enter number of bedrooms: "))

# Convert input into DataFrame (avoids warning)
new_data = pd.DataFrame([[size, bed]], columns=['Size', 'Bedrooms'])

# Scale input
new_scaled = scaler.transform(new_data)

# Predictions
pred_price = price_model.predict(new_scaled)
pred_occ = occ_model.predict(new_scaled)

# Output
print("Predicted Price:", round(pred_price[0], 2))
print("Predicted Occupants:", round(pred_occ[0]))
*/
```

## Output:
![multivariate linear regression model for predicting the price of the house and number of occupants in the house](sam.png)<img width="1062" height="79" alt="multivariate linear regression Ex -04" src="https://github.com/user-attachments/assets/3c3618bf-7b36-404a-a4c7-d13a781357f5" />



## Result:
Thus the program to implement the multivariate linear regression model for predicting the price of the house and number of occupants in the house with SGD regressor is written and verified using python programming.
