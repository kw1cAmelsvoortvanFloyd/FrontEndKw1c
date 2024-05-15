<script>
  import Header from "../../components/header.svelte";
  import Footer from "../../components/footer.svelte";

  let totalDonated = "2";
  let timesDonated = "1";
  let naam = "";
  let bedrag = "";

  const submitForm = () => {
    console.log(`Naam: ${naam}, Bedrag: ${bedrag}`);
    return false; // Prevent actual form submission
  };
</script>

<Header />
<body class="flex flex-col min-h-screen mt-32 lg:mt-0">
  <div
    class="flex flex-col lg:flex-row justify-center items-center lg:justify-between lg:items-start lg:min-h-[90vh] p-4 lg:p-0 w-full"
  >
    <div
      class="space-y-4 lg:space-y-0 lg:flex-row lg:gap-4 lg:ml-[15vw] lg:mt-[215px] text-center"
    >
      <div
        class="border-2 border-gray-400 min-w-64 max-h-[100px] bg-myBackground p-4 mx-auto mb-2"
      >
        <h1>Totaal aantal keer gedoneerd:</h1>
        <p>{timesDonated}</p>
      </div>
      <div
        class="border-2 border-gray-400 min-w-64 max-h-[100px] bg-myBackground p-4 mx-auto"
      >
        <h1>Totaal aantal gedoneerd:</h1>
        <p>{totalDonated}</p>
      </div>
    </div>

    <div
      class="mt-4 lg:mt-[215px] lg:mr-[32vw] border-2 border-gray-400 p-4 bg-myBackground mx-auto w-full max-w-md"
    >
      <form on:submit|preventDefault={submitForm} class="flex flex-col gap-4">
        <div>
          <label for="naam" class="block">Naam:</label>
          <input
            type="text"
            id="naam"
            bind:value={naam}
            class="border-2 border-gray-300 w-full"
          />
        </div>
        <div>
          <label for="bedrag" class="block">Bedrag:</label>
          <input
            type="text"
            id="bedrag"
            bind:value={bedrag}
            class="border-2 border-gray-300 w-full"
          />
        </div>
        <button type="submit" class="bg-blue-500 text-white px-4 py-2"
          >Doneren</button
        >
      </form>
    </div>
  </div>
</body>
<Footer />
