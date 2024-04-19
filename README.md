# Extrapolation-Assignment
This is my ICS3U extrapolation assignment. 

import pandas as pd
import matplotlib.pyplot as plt
import numpy as np
from sklearn.linear_model import LinearRegression

path = "/content/drive/MyDrive/Python_Data/population_data.csv"
df = pd.read_csv(path)

x = df['Year'].values.reshape(-1, 1)
y = df['Population'].values

model = LinearRegression()
model.fit(x, y)

a = np.arange(x.max() + 1, x.max() + 101).reshape(-1, 1)
b = model.predict(a)

def extrapolation():
    plt.plot(a.flatten(), b)
    plt.xlabel('Year')
    plt.ylabel('Population')
    plt.show()

def bar_graph():
    plt.bar(df['Year'], df['Population'])
    plt.xlabel('Year')
    plt.ylabel('Population')
    plt.show()

def line_graph():
    plt.plot(df['Year'], df['Population'])
    plt.xlabel('Year')
    plt.ylabel('Population Data')
    plt

choice = int(input("Choose:\n1. Extrapolation\n2. Bar graph\n3. Line graph\n"))

if choice == 1:
    extrapolation()
elif choice == 2:
    bar_graph()
elif choice == 3:
    line_graph()
