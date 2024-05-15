<script>
  import { onMount, onDestroy } from "svelte";
  import Car1 from "$lib/assets/Car1.jpeg";
  import Car2 from "$lib/assets/Car2.jpeg";
  import Hond1 from "$lib/assets/Hond1.jpg";
  import Hond2 from "$lib/assets/Hond2.jpg";
  import Hond3 from "$lib/assets/Hond3.jpg";
  import Hond4 from "$lib/assets/Hond4.jpeg";

  let images = [
    { url: Car1, alt: "kat, 2 jaar oud" },
    { url: Hond1, alt: "DOGGO2" },
    { url: Hond2, alt: "DOGGO3" },
    { url: Car2, alt: "kat, 4 jaar oud" },
    { url: Hond3, alt: "DOGGO3" },
    { url: Hond4, alt: "DOGGO3" },
  ];

  let currentIndex = 0;
  let interval;

  function nextImage() {
    currentIndex = (currentIndex + 1) % images.length;
  }

  onMount(() => {
    interval = setInterval(nextImage, 3000);
    return () => {
      clearInterval(interval);
    };
  });
</script>

<div class="slideshow-container">
  <img src={images[currentIndex].url} alt={images[currentIndex].alt} />
  <p>{currentIndex}</p>
</div>

<p></p>
