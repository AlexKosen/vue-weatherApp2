<script>
export default {
  data() {
    return {
      cities: [
        {
          city: "Cherkasy",
          adress: "latitude=49.44&longitude=32.06",
        },
        {
          city: "Kyiv",
          adress: "latitude=49.43&longitude=32.04",
        },
        {
          city: "Drabove-Bariatynske",
          adress: "latitude=49.94&longitude=32.29",
        },
        {
          city: "Berlin",
          adress: "latitude=52.52&longitude=13.41",
        },
        {
          city: "Paris",
          adress: "latitude=48.85&longitude=2.35",
        },
        {
          city: "London",
          adress: "latitude=51.51&longitude=-0.13",
        },
        {
          city: "New York",
          adress: "latitude=40.71&longitude=-74.01",
        },
        {
          city: "Washington",
          adress: "latitude=38.90&longitude=-77.04",
        },
      ],
      info: null,

      selectCity: "",

      currentWeather: [],

      date: new Date(),

      getCurrentGeolocation: " ",

      currentLocationCity: " ",

      iconsWeather: {
        0: "/images/icon-2.svg", //ясно
        1: "/images/icon-2.svg", //перважно ясно
        2: "/images/icon-3.svg", //мінлива хмарність
        3: "/images/icon-6.svg", //похмуро
        45: "/images/icon-8.svg", //туман
        48: "/images/icon-8.svg", //відкладення туману
        51: "/images/icon-7.svg", //мряка слабка
        53: "/images/icon-7.svg", //мряка помірна
        55: "/images/icon-8.svg", //мряка густа
        56: "/images/icon-9.svg", //крижаний дощ легкий
        57: "/images/icon-10.svg", //крижаний дощ щільний
        61: "/images/icon-9.svg", //дощ легкий
        63: "/images/icon-9.svg", //дощ помірний
        65: "/images/icon-10.svg", //дощ щільний
        66: "/images/icon-9.svg", //крижаний дощ легкий
        67: "/images/icon-10.svg", //крижаний дощ щільний
        71: "/images/icon-13.svg", //снігопад слабкий
        73: "/images/icon-13.svg", //снігопад помірний
        75: "/images/icon-14.svg", //снігопад сильний
        77: "/images/icon-13.svg", //снігові крупинки
        80: "/images/icon-9.svg", //дощ легкий
        81: "/images/icon-9.svg", //дощ помірний
        82: "/images/icon-10.svg", //дощ сильний
        85: "/images/icon-13.svg", //сніг невелий
        86: "/images/icon-14.svg", //сніг сильний
        95: "/images/icon-12.svg", //гроза слабка та помірна
        96: "/images/icon-11.svg", //гроза з градом невеликим
        99: "/images/icon-11.svg", //гроза з градом сильним
      },
    };
  },
  methods: {
    getRespons: function (cityAdress, nameCity, dataWeather = 0) {
      let url = `https://api.open-meteo.com/v1/forecast?${cityAdress}&hourly=temperature_2m,relativehumidity_2m,cloudcover,windspeed_10m,winddirection_10m&daily=weathercode,temperature_2m_max,temperature_2m_min,windspeed_10m_max&current_weather=true&timezone=Europe%2FLondon`;
      fetch(url)
        .then((response) => {
          if (response.ok) return response.json();
          else throw new Error(`Ошибка загрузки, код ${response.status}`);
        })
        .then((json) => {
          this.currentWeather.push(json, nameCity);
          console.log(this.currentWeather);
          console.log(this.currentWeather[0].daily);
          console.log(this.currentWeather[0].hourly.winddirection_10m[0]);
          console.log(
            this.currentWeather[0].hourly.winddirection_10m[
              this.getCurrentHours()
            ]
          );
        });
    },

    getMonth: function () {
      let month = [
        "Jan",
        "Fab",
        "Mar",
        "Apr",
        "May",
        "Jun",
        "Jul",
        "Aug",
        "Sep",
        "Oct",
        "Nov",
        "Dec",
      ];

      for (let i = 0; i < month.length; i++) {
        if (i == this.date.getMonth()) {
          return month[i];
        }
      }
    },

    getDay: function () {
      let day = [
        "Sunday",
        "Monday",
        "Tuesday",
        "Wednesday",
        "Thursday",
        "Friday",
        "Saturday",
      ];

      for (let i = 0; i < day.length; i++) {
        if (i == this.date.getDay()) {
          return day[i];
        }
      }
    },

    getNextDay: function (nDay) {
      let day = [
        "Sunday",
        "Monday",
        "Tuesday",
        "Wednesday",
        "Thursday",
        "Friday",
        "Saturday",
        "Sunday",
        "Monday",
        "Tuesday",
        "Wednesday",
        "Thursday",
        "Friday",
        "Saturday",
      ];
      for (let i = 0; i < day.length; i++) {
        if (i === this.date.getDay()) {
          return day[i + nDay];
        }
      }
    },

    getCurrentHours: function () {
      return this.date.getHours();
    },

    degToCompass: function (num) {
      const val = Math.floor(num / 45 + 0.5);
      const arr = [
        "North",
        "NorthEast",
        "East",
        "SouthEast",
        "South",
        "SouthWeast",
        "Weast",
        "NortWest",
      ];
      return arr[val % 8];
    },

    getIconWeather: function (n) {
      let img;
      for (let icon in this.iconsWeather) {
        if (icon == n) return this.iconsWeather[icon];
      }
    },

    maxTemp(nDay) {
      let temperature = this.currentWeather[0]?.daily.temperature_2m_max[nDay];
      return temperature == undefined ? " " : Math.round(temperature);
    },

    minTemp(nDay) {
      let temperature = this.currentWeather[0]?.daily.temperature_2m_min[nDay];
      return temperature == undefined ? " " : Math.round(temperature);
    },

    showWeatherSselectCity: function () {
      for (let city of this.cities) {
        if (this.selectCity == city.city) {
          this.currentWeather = [];
          this.getRespons(city.adress, city.city);
          this.selectCity = "";
        }
      }
    },
  },

  created() {
    navigator.geolocation.getCurrentPosition(
      (pos) => {
        this.getCurrentGeolocation = `latitude=${pos.coords.latitude}&longitude=${pos.coords.longitude}`;
        console.log("Longitude: " + pos.coords.longitude); // Выведем долготу
        console.log("Latitude: " + pos.coords.latitude); // Выведем широту
        console.log(this.getCurrentGeolocation);

        const query = new URLSearchParams({
          q: "",
          locale: "en",
          limit: "5",
          reverse: "true",
          debug: "false",
          point: `${pos.coords.latitude},${pos.coords.longitude}`,
          provider: "default",
          key: "6b3f94b0-c415-4e7d-9aa9-686125745976",
        }).toString();

        const resp = fetch(`https://graphhopper.com/api/1/geocode?${query}`, {
          method: "GET",
        })
          .then((resp) => resp.json())
          .then((obj) =>
            this.getRespons(this.getCurrentGeolocation, obj.hits[0].city)
          );
      },

      (error) => this.getRespons(this.cities[0].adress, this.cities[0].city),
      console.log(
        "Пожалуйста, разрешите доступ к использованию Вашей геолокации!"
      )
    );
  },

  computed: {
    currentTemp() {
      let temperature = this.currentWeather[0]?.current_weather.temperature;
      return temperature == undefined ? " " : Math.round(temperature);
    },
  },
};
</script>

<template>
  <div class="hero">
    <div class="container">
      <form action="#" class="find-location">
        <select v-model.lazy="selectCity">
          <option disabled value="">Find your location...</option>
          <option
            v-for="(city, index) of cities"
            v-bind:value="city.city"
            :key="index"
          >
            {{ city.city }}
          </option>
        </select>
        <!-- <input type="text" placeholder="Find your location..." /> -->
        <input
          type="submit"
          value="Find"
          v-on:click.prevent="showWeatherSselectCity"
        />
      </form>
    </div>
  </div>
  <div class="forecast-table">
    <div class="container">
      <div class="forecast-container">
        <div class="today forecast">
          <div class="forecast-header">
            <div class="day">{{ getDay() }}</div>
            <div class="date">
              {{ date.getDate() }} {{ getMonth() }} {{ date.getFullYear() }}
            </div>
          </div>
          <!-- .forecast-header -->
          <div class="forecast-content">
            <div class="location">{{ currentWeather[1] }}</div>
            <div class="degree">
              <div class="num">
                {{ currentTemp }}
                <sup>o</sup>C
              </div>
              <div class="forecast-icon">
                <img
                  :src="
                    getIconWeather(
                      currentWeather[0]?.current_weather.weathercode
                    )
                  "
                  alt=""
                  width="90"
                />
              </div>
            </div>
            <span
              ><img src="@/assets/images/icon-wind.png" alt="" />{{
                currentWeather[0]?.current_weather.windspeed
              }}
              km/h</span
            >
            <span
              ><img src="@/assets/images/icon-compass.png" alt="" />{{
                degToCompass(currentWeather[0]?.current_weather.winddirection)
              }}</span
            >
          </div>
        </div>
        <div class="forecast">
          <div class="forecast-header">
            <div class="day">{{ getNextDay(1) }}</div>
          </div>
          <!-- .forecast-header -->
          <div class="forecast-content">
            <div class="forecast-icon">
              <img
                :src="getIconWeather(currentWeather[0]?.daily.weathercode[1])"
                alt=""
                width="48"
              />
            </div>
            <div class="degree">{{ maxTemp(1) }}<sup>o</sup>C</div>
            <small>{{ minTemp(1) }}<sup>o</sup></small>
          </div>
        </div>
        <div class="forecast">
          <div class="forecast-header">
            <div class="day">{{ getNextDay(2) }}</div>
          </div>
          <!-- .forecast-header -->
          <div class="forecast-content">
            <div class="forecast-icon">
              <img
                :src="getIconWeather(currentWeather[0]?.daily.weathercode[2])"
                alt=""
                width="48"
              />
            </div>
            <div class="degree">{{ maxTemp(2) }}<sup>o</sup>C</div>
            <small>{{ minTemp(2) }}<sup>o</sup></small>
          </div>
        </div>
        <div class="forecast">
          <div class="forecast-header">
            <div class="day">{{ getNextDay(3) }}</div>
          </div>
          <!-- .forecast-header -->
          <div class="forecast-content">
            <div class="forecast-icon">
              <img
                :src="getIconWeather(currentWeather[0]?.daily.weathercode[3])"
                alt=""
                width="48"
              />
            </div>
            <div class="degree">{{ maxTemp(3) }}<sup>o</sup>C</div>
            <small>{{ minTemp(3) }}<sup>o</sup></small>
          </div>
        </div>
        <div class="forecast">
          <div class="forecast-header">
            <div class="day">{{ getNextDay(4) }}</div>
          </div>
          <!-- .forecast-header -->
          <div class="forecast-content">
            <div class="forecast-icon">
              <img
                :src="getIconWeather(currentWeather[0]?.daily.weathercode[4])"
                alt=""
                width="48"
              />
            </div>
            <div class="degree">{{ maxTemp(4) }}<sup>o</sup>C</div>
            <small>{{ minTemp(4) }}<sup>o</sup></small>
          </div>
        </div>
        <div class="forecast">
          <div class="forecast-header">
            <div class="day">{{ getNextDay(5) }}</div>
          </div>
          <!-- .forecast-header -->
          <div class="forecast-content">
            <div class="forecast-icon">
              <img
                :src="getIconWeather(currentWeather[0]?.daily.weathercode[5])"
                alt=""
                width="48"
              />
            </div>
            <div class="degree">{{ maxTemp(5) }}<sup>o</sup>C</div>
            <small>{{ minTemp(5) }}<sup>o</sup></small>
          </div>
        </div>
        <div class="forecast">
          <div class="forecast-header">
            <div class="day">{{ getNextDay(6) }}</div>
          </div>
          <!-- .forecast-header -->
          <div class="forecast-content">
            <div class="forecast-icon">
              <img
                :src="getIconWeather(currentWeather[0]?.daily.weathercode[6])"
                alt=""
                width="48"
              />
            </div>
            <div class="degree">{{ maxTemp(6) }}<sup>o</sup>C</div>
            <small>{{ minTemp(6) }}<sup>o</sup></small>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style>
.hero {
  background-image: url("@/assets/images/banner.png");
}
[v-cloak] {
  display: none;
}

@media screen and (max-width: 480px) {
  .forecast-container .forecast.today .degree .num {
    font-size: 5rem;
  }
}
</style>