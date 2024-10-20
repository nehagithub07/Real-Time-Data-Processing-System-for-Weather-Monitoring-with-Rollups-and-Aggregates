# Real-Time Data Processing System for Weather Monitoring

## Objective
This project aims to develop a real-time data processing system for monitoring weather conditions and generating summarized insights using rollups and aggregates. It continuously retrieves data from the OpenWeatherMap API to provide weather analysis for major Indian metros, with a focus on real-time data processing, alerting, and visualization.

## Features
- **Continuous Data Retrieval:** Automatically fetches weather data at configurable intervals from the OpenWeatherMap API.
- **Data Processing:** Converts and analyzes weather data for major Indian cities.
- **Daily Summaries:** Generates daily weather summaries including average, maximum, and minimum temperatures, as well as dominant weather conditions.
- **Alerting Mechanism:** Configurable thresholds for temperature and weather conditions that trigger alerts when breached.
- **Visualizations:** Displays daily summaries, trends, and triggered alerts via graphical representations.
- **Bonus Features:** Includes extended weather parameters and weather forecasts.

## Technologies Used
- **Backend:** Python (Flask)
- **Database:** MongoDB
- **Frontend:** HTML, CSS
- **Libraries:** Requests, PyMongo, Matplotlib
- **Version Control:** GitHub (mandatory for this assignment)

## Data Source
The system fetches real-time weather data from the OpenWeatherMap API. You must obtain a free API key from the [OpenWeatherMap website](https://openweathermap.org/api). Key weather parameters used:
- `main`: Main weather condition (e.g., Rain, Snow, Clear)
- `temp`: Current temperature (°C)
- `feels_like`: Perceived temperature (°C)
- `dt`: Data timestamp (Unix format)

## Non-Functional Considerations
### Security
- **API Key Management:** API keys are securely stored using environment variables to prevent exposure.
- **Data Validation:** All inputs are validated to protect against injection attacks and ensure data integrity.
- **Secure Communication:** The system is designed to support HTTPS for secure data transmission between the server and client.

### Performance
- **Caching:** Reduces the frequency of API calls and improves performance through caching.
- **Asynchronous Processing:** Uses asynchronous programming for concurrent API requests, reducing latency.
- **Scalability:** The architecture is designed to scale efficiently, supporting increased data loads and user traffic.
- **Database Optimization:** Indexes frequently accessed fields in MongoDB to optimize query performance and response times.

### Monitoring and Logging
- **Logging:** Tracks errors, performance metrics, and system events for troubleshooting and analysis.
- **Monitoring:** Implements monitoring tools to track system performance, uptime, and critical metrics.

## Setup Instructions
### Prerequisites
- Python 3.6+
- Virtual Environment
- MongoDB

### Steps to Install
1. **Clone the Repository:**
   ```bash
   git clone <repository-url>
   cd <repository-directory>
   ```
2. **Create a Virtual Environment:**
   ```bash
   python -m venv venv
   ```
3. **Activate the Virtual Environment:**
   - On Windows:
     ```bash
     venv\Scripts\activate
     ```
   - On macOS/Linux:
     ```bash
     source venv/bin/activate
     ```
4. **Install Required Dependencies:**
   ```bash
   pip install flask requests pymongo matplotlib
   ```
5. **Set up MongoDB:**
   Ensure MongoDB is running and update the MongoDB connection string in the `config.py` file.
6. **Configure API Key:**
   Obtain an API key from OpenWeatherMap and update the `config.py` file with your API key.
7. **Store Data:**
   - Run the following command to start storing weather data in MongoDB:
     ```bash
     python main.py
     ```
8. **Run the Flask Application:**
   ```bash
   python app.py
   ```

## Usage Instructions
### Data Retrieval
The system calls the OpenWeatherMap API at intervals to gather real-time weather data for major Indian cities like Delhi, Mumbai, Chennai, Bangalore, Kolkata, and Hyderabad.

### Data Processing
Each weather update includes:
- Conversion of temperature values from Kelvin to Celsius.
- Storage of processed data in MongoDB.

### Rollups and Aggregates
The system generates daily weather summaries, including:
- Average, maximum, and minimum temperatures.
- Dominant weather conditions.

### Alerting
The system triggers alerts based on pre-configured temperature and weather condition thresholds.

### Visualizations
Graphical representations of daily summaries, historical trends, and alert notifications.

## Test Cases
### System Setup
- Verify successful startup and connection to the OpenWeatherMap API.
### Data Retrieval
- Validate data retrieval and parsing from the API at regular intervals.
### Temperature Conversion
- Test conversion of temperatures from Kelvin to Celsius.
### Daily Weather Summary
- Simulate weather updates and validate accuracy of the daily summaries.
### Alerting
- Test the alert mechanism by simulating threshold breaches.

## Bonus Features
- **Extended Weather Parameters:** Includes parameters such as humidity and wind speed in rollups and aggregates.
- **Weather Forecasts:** Ability to retrieve and summarize forecast data for additional insights.

## GitHub Usage
- All codebase, build scripts, and configurations are stored in the GitHub repository.
- Proper commit messages are used to document changes.
- README and build instructions are provided for ease of setup and deployment.

## Non-Functional Features (Bonus)
- **Security Enhancements:** API keys stored securely, data validation implemented.
- **Performance Optimization:** Caching and asynchronous processing to reduce latency.
- **Scalability:** Designed to handle a growing user base and data load efficiently.

