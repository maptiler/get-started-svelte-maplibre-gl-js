<script>
	import { onMount } from "svelte";
	import { Map }  from "@onsvisual/svelte-maps";
	import maplibre from "maplibre-gl";

	let map;
	// State
	let zoom;
	let center = {};

	onMount(() => {
		map.addControl(new maplibre.NavigationControl(), 'top-left');
	})
</script>

<main>
	<Map id="map" 
		style="https://api.maptiler.com/maps/streets/style.json?key=YOUR_MAPTILER_API_KEY_HERE" 
		location={{lng: 16.62662018, lat: 49.2125578, zoom: 14}} 
		bind:map={map} bind:zoom={zoom} bind:center={center} />
</main>

<style>
	main {
		width: 100%;
		height: 100vh;
		position: relative;
	}
</style>