<!-- <script>
  import maplibreGl from "maplibre-gl";

  const key = "Z5oyxEHjNFqEUZE1KlEg";
  const map = new maplibregl.Map({
    container: "map", // container's id or the HTML element in which MapLibre GL JS will render the map
    style: `https://api.maptiler.com/maps/streets-v2/style.json?key=${key}`, // style URL
    center: [16.62662018, 49.2125578], // starting position [lng, lat]
    zoom: 14, // starting zoom
  });
  map.addControl(new maplibregl.NavigationControl(), "top-right");

  class searchControl {
    onAdd(map) {
      this._map = map;
      this._container = document.createElement("div");
      this._container.className = "maplibregl-ctrl";
      const _input = document.createElement("input");
      this._container.appendChild(_input);
      const geocoder = new maptiler.Geocoder({
        input: _input,
        key: key,
      });
      geocoder.on("select", function (item) {
        map.fitBounds(item.bbox);
      });
      return this._container;
    }
    onRemove() {
      this._container.parentNode.removeChild(this._container);
      this._map = undefined;
    }
  }
  map.addControl(new searchControl(), "top-left");
</script>

<div>
  <input type="search" name="geoloc" id="" />
</div>

<style>
  .maplibregl-ctrl {
    position: absolute;
    z-index: 1;
    background: #fff;
    padding: 10px;
    border-radius: 4px;
    box-shadow: 0 1px 2px rgba(0, 0, 0, 0.1);
  }
  .maplibregl-ctrl-top-left {
    top: 10px;
    left: 10px;
  }
  .maplibregl-ctrl-top-right {
    top: 10px;
    right: 10px;
  }
  .maplibregl-ctrl-bottom-left {
    bottom: 10px;
    left: 10px;
  }
  .maplibregl-ctrl-bottom-right {
    bottom: 10px;
    right: 10px;
  }
</style> -->
