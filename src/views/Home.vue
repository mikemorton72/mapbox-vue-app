<template>
  <div class="home">
    <div id="map" style="width: 800px; height: 450px"></div>
  </div>
</template>

<script>
import "mapbox-gl/dist/mapbox-gl.css";
import mapboxgl from "mapbox-gl"; // or "const mapboxgl = require('mapbox-gl');"

export default {
  mounted: function () {
    this.doMapBox();
  },
  methods: {
    doMapBox: function () {
      mapboxgl.accessToken = process.env.VUE_APP_MAP_BOX_API_KEY;
      const map = new mapboxgl.Map({
        container: "map", // container ID
        style: "mapbox://styles/mapbox/streets-v11", // style URL
        center: [-74.5, 40], // starting position [lng, lat]
        zoom: 9, // starting zoom
      });
    },
  },
};
</script>
