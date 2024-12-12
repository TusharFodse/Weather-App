# Weather App
# Weather Web Application

This is a simple weather web application that allows users to search for weather details of any city using OpenWeatherMap API. The application displays weather conditions, temperature, humidity, wind speed, and dynamically updates visuals based on the weather type.

---

## Features

- Search for weather information by city name.
- Displays:
  - Current temperature.
  - Weather description.
  - Humidity percentage.
  - Wind speed.
- Dynamic images that reflect the weather condition (e.g., clear, rain, snow).
- Handles errors for invalid city names.

---

## Technologies Used

- **HTML5**
- **CSS3**
- **JavaScript**
- **OpenWeatherMap API**

---

## Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/your-username/weather-web-app.git
   ```
2. Navigate to the project directory:
   ```bash
   cd weather-web-app
   ```
3. Open the `index.html` file in your browser to run the application.

---

## Usage

1. Open the web application in your browser.
2. Enter the city name in the search box.
3. Click the **Search** button.
4. The weather information for the city will be displayed, including:
   - Temperature (in Celsius).
   - Weather description.
   - Humidity percentage.
   - Wind speed (in Km/h).
   - Weather icon based on the conditions.
5. If the city is not found, an error message is displayed.

---

## Code Explanation

### Key JavaScript Elements

- **Query Selectors:**
  ```javascript
  const container = document.querySelector('.container');
  const search = document.querySelector('.search-box button');
  const weatherBox = document.querySelector('.weather-box');
  const weatherDetails = document.querySelector('.weather-details');
  const error404 = document.querySelector('.not-found');
  ```

- **API Key and URL:** Replace `APIKey` with your OpenWeatherMap API key.
  ```javascript
  const APIKey = 'your-api-key';
  const city = document.getElementById('search-btn').value;
  ```

- **Fetching Data:**
  ```javascript
  fetch(`https://api.openweathermap.org/data/2.5/weather?q=${city}&units=metric&appid=${APIKey}`)
    .then(response => response.json())
    .then(json => {
      // Update the UI based on the JSON response
    });
  ```

- **Dynamic Weather Icons:**
  ```javascript
  switch(json.weather[0].main) {
      case 'Clear':
          image.src = 'images/clear-new.png';
          break;
      case 'Rain':
          image.src = 'images/rain-new.png';
          break;
      case 'Snow':
          image.src = 'images/snow-new.png';
          break;
      case 'Clouds':
          image.src = 'images/cloud-new.png';
          break;
      default:
          image.src = 'images/clear-new.png';
  }


## Project Structure

```plaintext
weather-web-app/
|— index.html
|— styles.css
|— script.js
|— images/
    |— clear-new.png
    |— rain-new.png
    |— snow-new.png
    |— cloud-new.png
    |— mist-new.png


## Future Improvements

- Add additional weather parameters (e.g., sunrise/sunset times).
- Implement responsive design for mobile devices.
- Allow users to get weather data for their current location using geolocation.



## License

This project is licensed under the MIT License. Feel free to use, modify, and distribute this code.



## Acknowledgments

- [OpenWeatherMap API](https://openweathermap.org/api) for providing the weather data.
- Icons sourced from the application's images folder.

