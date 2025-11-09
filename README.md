This project focuses on analyzing Weather Data using Python, Pandas, and Matplotlib.
The goal is to clean, explore, and visualize weather patterns over time — such as temperature trends, humidity levels, wind speed, and other environmental parameters.

By leveraging data analysis libraries in Python, this project extracts insights from raw weather data, performs exploratory analysis, and generates visual reports.

🧠 Objectives

Load and clean a weather dataset using Pandas

Convert and manipulate date-time information

Analyze weather conditions such as temperature, humidity, and wind

Visualize trends over time using Matplotlib

Extract insights about variations in climate parameters

🧰 Tools & Libraries Used
Tool	Purpose
Python	Main programming language
Pandas	Data cleaning, manipulation, and analysis
Matplotlib	Data visualization
Jupyter Notebook / VS Code	Code execution environment
CSV Dataset	Source of weather data
📂 Dataset Information

The dataset (weather.csv) contains weather-related information such as:

Column Name	Description
date	Date and time of data recording
Summary	Short description of weather conditions
Precip Type	Type of precipitation (Rain/Snow)
Temperature (C)	Temperature in Celsius
Apparent Temperature (C)	Feels-like temperature
Humidity	Relative humidity
Wind Speed (km/h)	Speed of the wind
Wind Bearing (degrees)	Wind direction in degrees
Visibility (km)	Distance visible in kilometers
Pressure (millibars)	Atmospheric pressure
Daily Summary	Overall summary of the day
⚙️ Steps in Analysis
1️⃣ Import Libraries
import pandas as pd
import matplotlib.pyplot as plt

2️⃣ Load Dataset
df = pd.read_csv('weather.csv')

3️⃣ Data Inspection
df.info()
df.head()

4️⃣ Clean & Convert Data
df['date'] = pd.to_datetime(df['date'], errors='coerce')

5️⃣ Extract Month and Year
df['Month'] = df['date'].dt.month
df['Year'] = df['date'].dt.year

6️⃣ Visualize Temperature Trend
plt.figure(figsize=(12,6))
plt.plot(df['date'], df['Temperature (C)'], color='orange')
plt.title('Temperature Trend Over Time')
plt.xlabel('Date')
plt.ylabel('Temperature (°C)')
plt.grid(True)
plt.show()

7️⃣ Analyze Average Temperature per Year
avg_temp = df.groupby('Year')['Temperature (C)'].mean()
avg_temp.plot(kind='bar', color='skyblue')
plt.title('Average Temperature per Year')
plt.xlabel('Year')
plt.ylabel('Avg Temperature (°C)')
plt.show()

📊 Results & Observations

Visualized temperature changes over time.

Found yearly average temperature variation.

Extracted insights about humidity and pressure trends.

Demonstrated data cleaning and handling of date-time formats in Pandas.

🚀 How to Run the Project

Clone this repository

git clone https://github.com/abhirai452/WEATHER.git
cd WEATHER


Install dependencies

pip install pandas matplotlib


Run the Jupyter Notebook or Python file

jupyter notebook weather_analysis.ipynb


or

python weather_analysis.py

📈 Future Enhancements

Integrate real-time weather data using APIs (like OpenWeatherMap).

Add predictive modeling using machine learning.

Build an interactive dashboard using Plotly or Streamlit.

🧑‍💻 Author

Abhi Rai
Student | Data Science Enthusiast
📍 Working on Data Analytics Projects using Python
