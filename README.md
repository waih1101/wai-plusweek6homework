<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <link
      rel="stylesheet"
      href="https://stackpath.bootstrapcdn.com/bootstrap/4.5.2/css/bootstrap.min.css"
      integrity="sha384-JcKb8q3iqJ61gNV9KGb8thSsNjpSL0n8PARn9HuZOnIxN0hoP+VmmDGMN5t9UJ0Z"
      crossorigin="anonymous"
    />
    <title>Weather App</title>
<style>
        h1 {
        text-align: left;
        font-weight: 400;
        font-family:monospace; 
      }

      .container {
        margin: 0 auto;
        display: block;
        border-color: blue;
        background-color: #fff;
      }
      h2 {
        background: rgb(245, 243, 243);
        font-family: monospace;
        font-size: 15px;
        width: 170px;
      
      }

      p {
        display: inline;
        font-size: 40px;
        font-weight: 30px;
      }

      .weather-app {
        font-family: monospace;
        font-size: 20px;
        margin: 20px auto;
        max-width: 600px;
        padding: 15px;
        border: 1px solid grey;
        border-radius: 10px;
      }

   
      .form {
        border-color: blueviolet;

      }

      .go {
        background-color: lightskyblue;
        border-radius: 5px 5px;

      }

</style>
    
  </head>

  <body>
      <div class="container">
        <div class="weather-app">
          <form class="search-form" id="search-form">
            <div class="row">
              <div class="col-9">
                <input
                  type="search"
                  placeholder="Enter a city.."
                  autofocus="on"
                  autocomplete="off"
                  id="city-input"
                  class="form-control shadow-sm"
                />
              </div>
              <div class="col-3">
                <input
                  type="submit"
                  value="Search"
                  class="form-control btn btn-primary shadow-sm"
                />
              </div>
            </div>
          </form>

      <h1 id="city">
          Lisbon, Portugal
        </h1>
       <h2 id="date">
         Monday 11:27 
       </h2>

           <div class="float-left">
              <span class="temperature" id="temperature">23</span>
              <span class="units">
                <a href="#" id="celsius-link">°C</a> |
                <a href="#" id="fahrenheit-link">°F</a>
              </span>😎Sunny 
            </div>
       
      </br>
      </br>

      <div class="row">
        <div class="col-2">
          8/18
          <br />
          Tue
          <br />
          ⛅
          <br />
          18°C
        </div>

        <div class="col-2">
          8/19
          <br />
          Wed
          <br />
          ⛅
          <br />
          20°C
        </div>

        <div class="col-2">
          8/20
          <br />
          Thu
          <br />
          ☔
          <br />
          16°C
        </div>

        <div class="col-2">
            8/21
            <br />
            Fri
            <br />
            😎
            <br />
            23°C
          </div>

          <div class="col-2">
              8/22
              <br />
              Sat
              <br />
              ⛅
              <br />
              21°C
            </div>

            <div class="col-2">
                8/23
                <br />
                Sun
                <br />
                😎
                <br />
                23°C
              </div>

      </div>
      </div>
        <a href="https://github.com/waih1101/wai-plusweek6/commit/35a8fc7ac04b6340225174ebbcf29bc0e16d3b22">open-source-code</a> by Wai Ping Hui

<script>
    function formatDate(date) {
            let hours = date.getHours();
            if (hours < 10) {
                hours = `0${hours}`;
            }
            let minutes = date.getMinutes();
            if (minutes < 10) {
                minutes = `0${minutes}`;
            }

            let dayIndex = date.getDay();
            let days = [
                "Sunday",
                "Monday",
                "Tuesday",
                "Wednesday",
                "Thursday",
                "Friday",
                "Saturday"
            ];
            let day = days[dayIndex];

            return `${day} ${hours}:${minutes}`;
        }

        function search(event) {
            event.preventDefault();
            let cityElement = document.querySelector("#city");
            let cityInput = document.querySelector("#city-input");
            cityElement.innerHTML = cityInput.value;
        }

        function convertToFahrenheit(event) {
            event.preventDefault();
            let temperatureElement = document.querySelector("#temperature");
            temperatureElement.innerHTML = 66;
        }

        function convertToCelsius(event) {
            event.preventDefault();
            let temperatureElement = document.querySelector("#temperature");
            temperatureElement.innerHTML = 19;
        }

        let dateElement = document.querySelector("#date");
        let currentTime = new Date();
        dateElement.innerHTML = formatDate(currentTime);

        let searchForm = document.querySelector("#search-form");
        searchForm.addEventListener("submit", search);

        let fahrenheitLink = document.querySelector("#fahrenheit-link");
        fahrenheitLink.addEventListener("click", convertToFahrenheit);

        let celsiusLink = document.querySelector("#celsius-link");
        celsiusLink.addEventListener("click", convertToCelsius);

</script>

</body>
</html>
