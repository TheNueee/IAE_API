<template>
  <link
    href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/css/bootstrap.min.css"
    rel="stylesheet"
    integrity="sha384-QWTKZyjpPEjISv5WaRU9OFeRpok6YctnYmDr5pNlyT2bRjXh0JMhjY6hW+ALEwIH"
    crossorigin="anonymous"
  />
  <!-- <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/js/bootstrap.bundle.min.js" integrity="sha384-YvpcrYf0tY3lHB60NNkmXc5s9fDVZLESaAA55NDzOxhy9GkcIdslK1eN7N6jIeHz" crossorigin="anonymous"></script> -->
  <div v-for="country in countries" v-bind:key="country.index">
    <div class="card mx-4 my-3" style="width: 18rem">
      <img :src="country.country_logo" class="card-img-top" alt="..." />
      <div class="card-body">
        <p class="card-text">
          {{ country.country_name }}
        </p>
      </div>
    </div>
  </div>
</template>

<script>
// const axios = require('axios');
import axios from "axios";
export default {
  name: "bola",
  data() {
    return {
      countries: [],
    };
  },
  mounted() {
    axios({
      method: "get",
      url: "https://apiv3.apifootball.com/?action=get_countries&APIkey=c26aeba1cb458a68e41e0386ad18928a2e6646eb9edbddaa311c21ffa3334320",
      responseType: "json",
    }).then((response) => {
      //   console.log(response.data);
      this.countries = response.data;
    });
  },
};

// Make a GET request to a URL
</script>

<style></style>
