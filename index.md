<title>Place the geocoder input outside the map</title>
<script src="https://api.mapbox.com/mapbox-gl-js/v2.7.0/mapbox-gl.js"></script> 
<style> body { margin: 0; padding: 0; } #map { position: absolute; top: 0; bottom: 0; width: 100%; } </style> 
<script src="https://api.mapbox.com/mapbox-gl-js/plugins/mapbox-gl-geocoder/v4.7.2/mapbox-gl-geocoder.min.js"></script> 
<style> .geocoder { position: absolute; z-index: 1; width: 50%; left: 50%; margin-left: -25%; top: 10px; } .mapboxgl-ctrl-geocoder { min-width: 100%; } #map { margin-top: 75px; } </style>
<script> 
mapboxgl.accessToken = 'pk.eyJ1IjoiZ3VycHJlZXRhY2hpbnQiLCJhIjoiY2wwMTl0ZjhzMDI2YzNscGEybXQ2MnNvbiJ9.aNZsNi-jXP_wVCH47oNXzQ'; const map = new mapboxgl.Map({ container: 'map', style: 'mapbox://styles/gurpreetachint/cl01af2aj004v15po09nztlnd', center: [22.6729, 75.8577], zoom: 10 }); // Add the control to the map. const geocoder = new MapboxGeocoder({ accessToken: mapboxgl.accessToken, mapboxgl: mapboxgl }); map.addControl( new mapboxgl.GeolocateControl({ positionOptions: { enableHighAccuracy: true }, // When active the map will receive updates to the device's location as it changes. trackUserLocation: true, // Draw an arrow next to the location dot to indicate which direction the device is heading. showUserHeading: true }) ); document.getElementById('geocoder').appendChild(geocoder.onAdd(map)); </script>
