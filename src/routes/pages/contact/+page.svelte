<script>
   import Header from "../../components/header.svelte";
   import Footer from "../../components/footer.svelte";

  let naam = '';
  let email = '';
  let vraag = '';
  let nieuwsbrief = false;

  const submitForm = () => {
    // just log to the console no database yet
    console.log({ naam, email, vraag, nieuwsbrief });
  };
</script>

<Header />
<body>
   <div class="border-2 border-gray-400 mt-[215px] max-w-96 mr-auto ml-auto p-2">
      
      <form on:submit|preventDefault={submitForm} class="space-y-4">
      <div>
         <label for="naam" class="block text-sm font-medium text-gray-700">Naam</label>
         <input type="text" id="naam" bind:value={naam} class="mt-1 block w-full rounded-md border-gray-300 shadow-sm focus:border-indigo-500 focus:ring-indigo-500 sm:text-sm" required>
      </div>
      
      <div>
         <label for="email" class="block text-sm font-medium text-gray-700">Email</label>
         <input type="email" id="email" bind:value={email} class="mt-1 block w-full rounded-md border-gray-300 shadow-sm focus:border-indigo-500 focus:ring-indigo-500 sm:text-sm" required>
      </div>
         
      <div>
         <label for="vraag" class="block text-sm font-medium text-gray-700">Vraag</label>
         <textarea id="vraag" bind:value={vraag} class="mt-1 block w-full rounded-md border-gray-300 shadow-sm focus:border-indigo-500 focus:ring-indigo-500 sm:text-sm" required></textarea>
      </div>
      
      <div class="flex items-start">
         <div class="flex items-center h-5">
            <input id="nieuwsbrief" type="checkbox" bind:checked={nieuwsbrief} class="focus:ring-indigo-500 h-4 w-4 text-indigo-600 border-gray-300 rounded">
         </div>
         <div class="ml-3 text-sm">
            <label for="nieuwsbrief" class="font-medium text-gray-700">Nieuwsbrief</label>
         </div>
       </div>
      
         <button type="submit" class="inline-flex justify-center py-2 px-4 border border-transparent shadow-sm text-sm font-medium rounded-md text-white bg-indigo-600 hover:bg-indigo-700 focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-indigo-500">
            Submit
         </button>
      </form>
   </div>
</body>

<Footer />