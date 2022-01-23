<template>
  <div style="height: 2000px" id="map">
  </div>
</template>

<script>
import "leaflet/dist/leaflet.css";
import L from "leaflet";

export default {
  data: () => ({
    map: "",
  }),

  mounted() {
    this.map = L.map("map", {
      renderer: L.svg(),
    });
    this.map.setView(new L.LatLng(24.82159712722345, 54.6596646308899), 10);

    L.tileLayer(
      "https://api.mapbox.com/styles/v1/{id}/tiles/{z}/{x}/{y}?access_token=YOUR_ACCESS_TOKEN",
      {
        attribution:
          'Map data &copy; <a href="https://www.openstreetmap.org/">OpenStreetMap</a> contributors, <a href="https://creativecommons.org/licenses/by-sa/2.0/">CC-BY-SA</a>, Imagery © <a href="https://www.mapbox.com/">Mapbox</a>',
        maxZoom: 25,
        id: "mapbox/streets-v11",
        tileSize: 512,
        zoomOffset: -1,
        accessToken:
          "YOUR_ACCESS_TOKEN",
      }
    ).addTo(this.map);
  
  },
};
</script>
