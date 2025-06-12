# API-INTEGRATION-AND-DATA-VISUALIZATION
#COMPANY:CODETECH IT SOLUTIONS

#NAME:BEHARA VAISHNAVI PATNAIK

#INTERN ID:CT04DF34

#DOMAIN:PYTHON PROGRAMMING

#DURATION:4 WEEKS

#MENTOR:NEEELA SANTOSH

Problem statement: USE PYTHON TO FETCH DATA FROM A PUBLIC API (E.G., OPENWEATHERMAP) AND CREATE VISUALIZATIONS USING MATPLOTLIB OR SEABORN. Report: Fetching and Visualizing Weather Data Using Python

📌Objective

To fetch real-time weather data for the city of Visakhapatnam from the OpenWeatherMap public API and visualize key weather parameters such as Temperature, Feels Like temperature, and Humidity using a bar chart.

📌Tools and Libraries Used

requests: To send HTTP requests to the OpenWeatherMap API and retrieve weather data.

matplotlib.pyplot: To create a bar chart visualization of the weather parameters.

📌Step-by-Step Code Explanation

Importing Libraries python Copy Edit import requests import matplotlib.pyplot as plt requests is used to handle HTTP requests. matplotlib.pyplot is used for plotting the bar chart.
Defining API Access and City:
city_name = "Hyderabad"

api_key = "7f3fe070fb641332807ba83b1e35dc6e"

url = f"https://api.openweathermap.org/data/2.5/weather?q={city_name}&appid={api_key}&units=metric"

city_name: The city for which weather data is fetched.

api_key: Personal API key from OpenWeatherMap (required to access their data).

url: The full API endpoint URL.

units=metric ensures temperature is in Celsius.

Fetching Weather Data:
response = requests.get(url)

Sends a GET request to the API endpoint.

response contains the server’s reply.

Checking Response Status and Extracting Data:
if response.status_code == 200:

data = response.json()

temp = data['main']['temp']

feels_like = data['main']['feels_like']

humidity = data['main']['humidity']

weather_desc = data['weather'][0]['description']

print('Weather is', weather_desc)

print('Current Temperature is', temp)

print('Current Temperature Feels like is', feels_like)

print('Humidity is', humidity)
📌Check if response is successful (status_code == 200).

Parse JSON data to extract:

->Temperature (temp)

->Feels Like temperature (feels_like)

->Humidity percentage (humidity)

->Weather description (weather_desc)

Print the fetched weather details.

Preparing Data for Visualization:
labels = ['Temperature (°C)', 'Feels Like (°C)', 'Humidity (%)']

values = [temp, feels_like, humidity]

colors = ['blue', 'red', 'green']

->Labels describe each bar on the chart.

->Values hold the corresponding numeric data.

->Colors assigned to each bar for visual clarity.

Creating and Displaying the Bar Chart:
plt.bar(labels, values, color=colors)

plt.title(f'Current Weather Conditions: {weather_desc.capitalize()}')

plt.ylim(0, max(values) + 10)

for i, v in enumerate(values):

plt.text(i, v + 1, f"{v:.1f}", ha='center')
plt.show()

->Create a bar chart with labels and values.

->Title shows the weather condition description.

->Y-axis limit is set dynamically to give space above the tallest bar.

->Data labels (plt.text) show exact values above each bar.

->plt.show() renders the plot.

Handling Error Responses:
else: print(f'Response code is {response.status_code}')

->Prints an error message if API call was unsuccessful.

📌Sample Output:

->Weather is overcast clouds

->Current Temperature is 28.39

->Current Temperature Feels like is 32.24

->Humidity is 75

And a bar chart with three bars showing Temperature, Feels Like temperature, and Humidity.

📌Summary This program effectively: Connects to an external API to get live data.Parses JSON weather data.Visualizes temperature and humidity parameters in an easy-to-understand bar chart.Such automation can be extended for multiple cities, longer forecast data, or integrated into dashboards.

#OUTPUT:
