<script>
  import Header from "../../components/header.svelte";
  import Footer from "../../components/footer.svelte";
  let contentText = [
    {
      title: "Over Ons",
      content: `Artemis dierenopvang is een opvang waar in principe ieder dier in nood welkom is.
      Onze organisatie richt zich voornamelijk op huisdieren en wij zijn in regio Den Bosch de opvang met de meeste huisdieren.
      Wij werken vanuit de gedachte dat ieder dier die hulp nodig heeft geholpen moet worden ongeacht waar het dier geboren is, een ziekte of handicap heeft of dat de eigenaar wel of geen geld heeft voor de afstandskosten. Deze werkwijze is afwijkend van de meeste opvangen.

      Het doel van onze stichting is het opvangen van deze 'overbodige' dieren, deze verzorging en eventueel training te geven en vervolgens op zoek te gaan naar een liefdevolle nieuwe baas.
      Wij vangen zowel Nederlandse dieren op als dieren die in het buitenland geboren zijn. Deze laatste groep wordt veelal onbegrepen en dreigt vaak tussen wal en schip te belanden. Helaas worden dieren nog vaak van een foto uitgezocht en vervolgens naar Nederland gestuurd. Met deze plaatsingen gaat het regelmatig mis en er is dan geen opvang voor deze dieren. Om te voorkomen dat ze op verkoopssites belanden en vervolgens van hand tot hand gaan om nog meer trauma´s op te lopen richten wij ons op de opvang voor deze dieren. Bij ons komen ze tot rust, worden ze eventueel getraind en gaan we vanuit daar op zoek naar een definitief thuis.
      Wij werken vanuit de gedachte dat op ieder potje een deksel past en er uiteindelijk een liefdevol thuis voor ieder dier komt. Indien het dier zich prima voelt in de opvang is deze welkom zolang nodig is. Wij hanteren dan ook een absoluut NO KILL beleid en euthanasie is alleen aan de orde bij ondragelijk lijden.

      Omdat ieder dier een tweede kans verdient!`,
    },
    {
      title: "Nieuws",
      content:
        "Uitbreiding van Onze Faciliteiten\n\nDankzij de ongekende steun van onze gemeenschap en gulle donaties, hebben we onze faciliteiten kunnen uitbreiden. Met deze uitbreiding kunnen we nu nog meer dieren een veilige haven bieden. Deze nieuwe ruimte is specifiek ontworpen om de dieren die bij ons komen meer comfort en een betere gezondheidszorg te bieden. Daarnaast kunnen we nu ook meer gespecialiseerde trainingssessies aanbieden om dieren beter voor te bereiden op hun toekomstige thuis.\n\nVernieuwde Website\n\nWe hebben onze website een opfrisbeurt gegeven! Onze vernieuwde site is nu gebruiksvriendelijker en biedt uitgebreide informatie over onze werkwijze, de dieren die we opvangen, en hoe u kunt helpen. Bezoek onze vernieuwde site om meer te leren over onze missie, beschikbare dieren voor adoptie en hoe u een verschil kunt maken door donaties, vrijwilligerswerk, of adoptie.",
    },
  ];
</script>

<Header />
<body class="mt-32 lg:mt-0">
  <div class="flex justify-center items-center min-h-screen">
    <div
      class="flex flex-col md:flex-row md:gap-10 lg:gap-20 justify-center items-center w-full lg:max-w-4xl"
    >
      {#each contentText as { title, content }}
        <div class="flex flex-col items-center gap-4 my-4 w-full md:max-w-md">
          <div
            class="bg-myHeaderButton border-black border-2 border-solid rounded-3xl p-2 min-w-20"
          >
            <p class="text-center">{title}</p>
          </div>
          <div
            class="bg-myBackground border-black border-2 border-solid rounded-3xl p-4 max-w-lg w-full min-h-[450px] max-h-[450px] overflow-auto"
          >
            <p>{content}</p>
          </div>
        </div>
      {/each}
    </div>
  </div>
</body>
<Footer />
