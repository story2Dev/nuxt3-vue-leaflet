<template>
  <div style="height: 100vh; width: 100%" id="map">
    <client-only>
      <l-map
        :useGlobalLeaflet="false"
        ref="map"
        v-model:zoom="zoom"
        :center="[17.969417, 102.621294]"
      >
        <l-tile-layer
          url="https://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png"
          layer-type="base"
          name="OpenStreetMap"
        ></l-tile-layer>
        <l-marker
          v-for="marker in markers"
          :key="marker.id"
          :lat-lng="marker.latLng"
        ></l-marker>
      </l-map>
    </client-only>
  </div>
</template>

<script>
import "leaflet/dist/leaflet.css";
import { LMap, LTileLayer, LMarker } from "@vue-leaflet/vue-leaflet";

export default {
  components: {
    LMap,
    LTileLayer,
    LMarker,
  },
  data() {
    return {
      zoom: 7,
      markers: [
        {
          id: 1,
          latLng: [17.969417, 102.621294],
          icon: {
            iconUrl: "https://img.icons8.com/color/48/000000/marker.png",
            iconSize: [48, 48],
            iconAnchor: [24, 48],
          },
          draggable: true,
        },
        {
          id: 2,
          latLng: [17.969417, 103.621294],
          icon: {
            iconUrl: "https://img.icons8.com/color/48/000000/marker.png",
            iconSize: [48, 48],
            iconAnchor: [24, 48],
          },
          draggable: true,
        },
      ],
    };
  },
};
</script>

<style></style>
