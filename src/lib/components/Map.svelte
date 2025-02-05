<link rel="stylesheet" href="https://api.mapbox.com/mapbox-gl-js/plugins/mapbox-gl-geocoder/v5.0.3/mapbox-gl-geocoder.css" type="text/css">
<script>
import mapboxgl from "mapbox-gl";
import MapboxGeocoder from "@mapbox/mapbox-gl-geocoder";
import { onMount } from "svelte";


mapboxgl.accessToken = import.meta.env.VITE_MAPBOX_API_KEY;

onMount(() => {
    const map = new mapboxgl.Map({
        container: "map",
        style: "mapbox://styles/mapbox/streets-v12",
        center: [-74.5, 40],
        zoom: 9,
    });
    map.addControl(
        new MapboxGeocoder({
            accessToken: import.meta.env.VITE_MAPBOX_API_KEY,
            mapboxgl: mapboxgl
        })
    );
});
</script>



<div id="map" class="h-1/2 w-screen absolute"></div>