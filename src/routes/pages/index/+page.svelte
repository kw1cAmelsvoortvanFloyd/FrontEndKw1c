<script>
  import { onMount } from "svelte";
  import Header from "../../components/header.svelte";
  import Footer from "../../components/footer.svelte";
  import Car1 from "$lib/assets/Car1.jpeg";
  import Car2 from "$lib/assets/Car2.jpeg";
  import Hond1 from "$lib/assets/Hond1.jpg";
  import Hond2 from "$lib/assets/Hond2.jpg";
  import Hond3 from "$lib/assets/Hond3.jpg";
  import Hond4 from "$lib/assets/Hond4.jpeg";

  let contentText = [
    {
      title: "Nieuws",
      content: `Uitbreiding van Onze Faciliteiten
      
      Dankzij de ongekende steun van onze gemeenschap en gulle donaties, hebben we onze faciliteiten kunnen uitbreiden. Met deze uitbreiding kunnen we nu nog meer dieren een veilige haven bieden. Deze nieuwe ruimte is specifiek ontworpen om de dieren die bij ons komen meer comfort en een betere gezondheidszorg te bieden. Daarnaast kunnen we nu ook meer gespecialiseerde trainingssessies aanbieden om dieren beter voor te bereiden op hun toekomstige thuis.

      Vernieuwde Website

      We hebben onze website een opfrisbeurt gegeven! Onze vernieuwde site is nu gebruiksvriendelijker en biedt uitgebreide informatie over onze werkwijze, de dieren die we opvangen, en hoe u kunt helpen. Bezoek onze vernieuwde site om meer te leren over onze missie, beschikbare dieren voor adoptie en hoe u een verschil kunt maken door donaties, vrijwilligerswerk, of adoptie.`,
    },
  ];
  let Images = [
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
    currentIndex = (currentIndex + 1) % Images.length;
  }

  onMount(() => {
    interval = setInterval(nextImage, 3000);
    return () => {
      clearInterval(interval);
    };
  });
</script>

<Header />
<body>
  <div
    class="flex flex-col lg:flex-row justify-center items-center min-h-screen gap-4 mt-24 lg:mt-0"
  >
    {#each contentText as { title, content }}
      <div class="flex flex-col items-center gap-4 px-4">
        <div
          class="bg-myHeaderButton border-black border-2 rounded-3xl p-2 min-w-[200px]"
        >
          <p class="text-center">{title}</p>
        </div>
        <div
          class="bg-myBackground border-black border-2 rounded-3xl p-2 max-w-full lg:max-w-lg min-w-full lg:min-w-[300px] overflow-auto"
        >
          <p>{content}</p>
        </div>
      </div>
    {/each}
    <div
      class="bg-myBackground border-black border-2 rounded-3xl p-2 max-w-[420px] min-w-[420px] max-h-[420px] min-h-[420px] lg:max-w-[420px] lg:min-w-[420px] lg:max-h-[420px] lg:min-h-[420px] overflow-hidden flex justify-center items-center"
    >
      <img
        src={Images[currentIndex].url}
        alt={Images[currentIndex].alt}
        class="max-w-full max-h-full object-contain rounded-3xl"
      />
    </div>
  </div>
</body>
<Footer />
