<template>
  <v-container>
    <h1 class="display-1 text-center">Weather App</h1>
    <v-flex xs12 class="mt-4">
      <v-card color="blue-grey darken-2" dark>
        <v-card-text>
            <v-layout justify-center>
              <v-flex class="text-center">
                  <h4>Temperature</h4>
                  <h1 class="display-1"> {{weather.name}} </h1>
                  <img :src="icon" alt="weather icon">
                  <h3> {{temperature}} <span> &#176; C </span>  </h3>
                  <h2> {{description}} </h2>
              </v-flex>
            </v-layout>
        </v-card-text>
      </v-card>
    </v-flex>
    <v-flex xs12 class="mt-6">
      <v-form @submit.prevent="getWeatherData">
        <v-text-field
          v-model="city"
          label="Enter City Name"
          placeholder="Eg.: Dhaka"
          outlined
          clearable
        ></v-text-field>
      </v-form>
    </v-flex>
  </v-container>
</template>

<script>
export default {
  head() {
    return {
      title: "Weather App",
    };
  },
  data() {
    return {
      city: "London",
      weather: {},
    };
  },
  created() {
    this.getWeatherData();
  },
  methods: {
    getWeatherData() {
      this.$axios
        .$get(
          `https://api.openweathermap.org/data/2.5/weather?q=${this.city}&appid=66c5ec1d687192f2bc42bc6f1a756078`
        )
        .then((res) => (this.weather = JSON.parse(JSON.stringify(res))));
    },
  },
  computed:{
      icon(){
          return this.weather.weather ? `https://openweathermap.org/img/w/${this.weather.weather[0].icon}.png`: '';
      },
      temperature: function(){
          return this.weather.main ? (this.weather.main.temp - 273.15).toFixed(1) : '';
      },
      description: function(){
          return this.weather.weather ? (this.weather.weather[0].description):'';
      }
  }
};
</script>

<style>
</style>