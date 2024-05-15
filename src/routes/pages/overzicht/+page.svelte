<script>
  import Header from "../../components/header.svelte";
  import Footer from "../../components/footer.svelte";
  import testImage from "$lib/assets/Artemis_logo_cropped.png";
  import Car1 from "$lib/assets/Car1.jpeg";
  import Car2 from "$lib/assets/Car2.jpeg";
  import Hond1 from "$lib/assets/Hond1.jpg";
  import Hond2 from "$lib/assets/Hond2.jpg";
  import Hond3 from "$lib/assets/Hond3.jpg";
  import Hond4 from "$lib/assets/Hond4.jpeg";

  let images = [
    { url: Car1, alt: "Car, 2 years old" },
    { url: Hond1, alt: "Dog 1" },
    { url: Hond2, alt: "Dog 2" },
    { url: Car2, alt: "Car, 4 years old" },
    { url: Hond3, alt: "Dog 3" },
    { url: Hond4, alt: "Dog 4" },
  ];
</script>

<Header />
<body class="mb-32 lg:mb-0 bg-white">
  <div class="flex flex-col-reverse lg:flex-row justify-between min-h-screen">
    <div class="lg:w-1/2 w-full p-4 mt-4 lg:mt-0 overflow-auto">
      <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-4">
        {#each images as { url, alt }}
          <div class="border-black border-2 rounded-3xl p-2">
            <img
              src={url}
              {alt}
              class="w-full h-auto max-h-[250px] rounded-lg object-cover"
            />
          </div>
        {/each}
      </div>
    </div>

    <div class="lg:w-1/2 w-full flex justify-center items-center p-4">
      <div class="border-2 border-gray-400 rounded-lg overflow-hidden">
        <iframe
          title="Location"
          src="https://www.google.com/maps/embed?pb=!1m14!1m8!1m3!1d19790.689269681192!2d5.2826766!3d51.681142!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x47c6ee83eb830f4d%3A0x323f0a18f828da5c!2sJeroen%20Bosch%20Ziekenhuis!5e0!3m2!1sen!2snl!4v1710921554904!5m2!1sen!2snl"
          class="w-full"
          style="min-height: 300px; height: 100%;"
        >
        </iframe>
      </div>
    </div>
  </div>
</body>
<Footer />
