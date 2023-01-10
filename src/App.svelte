<script>
  import { onMount } from "svelte";
  import { Map } from "@onsvisual/svelte-maps";
  import maplibre from "maplibre-gl";
  import { Marker } from "maplibre-gl";
  import Navbar from "./components/Navbar.svelte";
  import SearchBar from "./components/SearchBar.svelte";

  let map;
  // State
  let zoom;
  let center = {};

  onMount(() => {
    new Marker({ color: "red" }).setLngLat([-75.49375, 39.05163]).addTo(map);
    map.addControl(new maplibre.NavigationControl(), "top-left");
    map.addControl(new maplibre.GeolocateControl(), "top-right");
    map.addControl(new maplibre.FullscreenControl(), "top-right");
    map.addControl(new maplibre.ScaleControl(), "bottom-right");
    map.ScaleControl({ maxWidth: 80, unit: "imperial" });
  });
</script>

<main>
  <Navbar />
  <SearchBar />
  <Map
    id="map"
    style="https://api.maptiler.com/maps/streets/style.json?key=Z5oyxEHjNFqEUZE1KlEg"
    location={{ lng: -75.49375, lat: 39.05163, zoom: 24 }}
    bind:map
    bind:zoom
    bind:center
  />
</main>

<style>
  main {
    width: 100%;
    height: calc(100vh - 83px);
    position: relative;
  }
</style>
