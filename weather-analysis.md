# Weather Data Analysis

You have been provided with a function that fetches weather data from the Open-Meteo API for a given latitude and longitude. The API returns an object with hourly weather data, including wind speed, temperature, and relative humidity.

Sample API Call:
```
curl "https://api.open-meteo.com/v1/forecast?latitude=49.2827&longitude=123.1207&past_days=10&hourly=temperature_2m,relative_humidity_2m,wind_speed_10m"
```
Response:

```
{
  "hourly": {
    "time": ["2022-06-19T00:00","2022-06-19T01:00", ...]
    "wind_speed_10m": [3.16,3.02,3.3,3.14,3.2,2.95, ...],
    "temperature_2m": [13.7,13.3,12.8,12.3,11.8, ...],
    "relative_humidity_2m": [82,83,86,85,88,88,84,76, ...],
  }
}
```


Your task is to implement the following functions:

1. Expose an API which accepts a lat and long and returns the weather analysis
    Response Format:
   ```
   {
      "averageWindSpeed": 3.0,
      "maxTemparuture": 13.9,
      "humidityOver80": 5
   }
   ```

3. `calculateAverageWindSpeed(data []float64) float64`
  This function takes a slice of wind speed values and calculates the average wind speed.
  Return the average wind speed as a float64.
2. `findMaxTemperature(data []float64) (float64, int)`
  This function takes a slice of temperature values and finds the maximum temperature.
  Return the maximum temperature as a float64 and its index in the slice as an int.
3. `countHumidityOverThreshold(data []float64, threshold float64) int`
  This function takes a slice of relative humidity values and a threshold value.
  Count the number of times the relative humidity exceeds the threshold.
  Return the count as an int.

