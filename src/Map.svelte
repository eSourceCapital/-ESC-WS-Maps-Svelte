<script>
  // import mapStyles from './map-styles'; // optional

  let container;
  let map;
  let marker;
  let zoom = 8;
  let center = { lat: -34.397, lng: 150.644 };

  import { onMount } from "svelte";

  function placeMarker(location) {
    let marker = new google.maps.Marker({
      position: location,
      map: map,
    });
  }

  onMount(async () => {
    map = new google.maps.Map(container, {
      zoom,
      center,
      //    styles: mapStyles // optional
    });
    google.maps.event.addListener(map, "click", function (event) {
      placeMarker(event.latLng);
    });
    placeMarker(center);
  });
</script>

<div class="full-screen" bind:this={container} />

<style>
  .full-screen {
    width: 50vw;
    height: 50vh;
  }
</style>
