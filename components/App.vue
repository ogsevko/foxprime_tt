<template>
  <div class="app">
    <AppHeader />
    <AddCity
      @add-city="addCity"
    />
    <WeatherTable
      :cities="citiesWithWeather"
    />
  </div>
</template>

<script>
import AppHeader from './AppHeader'
import AddCity from './AddCity'
import WeatherTable from './WeatherTable'

export default {
  name: 'App',
  components: {
    AppHeader,
    AddCity,
    WeatherTable
  },
  data () {
    return {
      cities: [],
      citiesWithWeather: []
    }
  },
  updated () {
    for (let i = 0; i < this.cities.length; i++) {
      const weatherData = this.getWeather(this.cities[i].name)
      weatherData.id = this.cities.id
      weatherData.name = this.cities.name
      this.citiesWithWeather.push(weatherData)
    }
    console.log(this.citiesWithWeather)
  },
  methods: {
    addCity (newCity) {
      this.cities = [...this.cities, newCity]
    },
    getWeather (cityName) {
      let weather
      const url = `https://api.openweathermap.org/data/2.5/weather?q=${cityName}&appid=7061e2a20d601340c9069314b528cc61&units=metric`

      fetch(url)
        .then(response => response.json())
        .then((data) => {
          weather = data
        })
        .catch(error => error)

      return weather
    }
  }
}
</script>
