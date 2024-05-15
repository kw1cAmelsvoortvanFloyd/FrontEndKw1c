<script>
  import { onMount } from "svelte";
  import Artemislogo from "$lib/assets/Artemis_logo_cropped.png";

  let headerItems = [
    { page: "Home", location: "pages/index" },
    { page: "Overzicht", location: "pages/overzicht" },
    { page: "Contact", location: "pages/contact" },
    { page: "Doneer", location: "pages/doneer" },
    { page: "Over Ons", location: "pages/overOns" },
  ];

  let mobileMenuOpen = false;

  function toggleMobileMenu() {
    mobileMenuOpen = !mobileMenuOpen;
  }
</script>

<header>
  <div class="bg-myBlue fixed top-0 flex items-center w-screen z-50">
    <div class="w-24 sm:w-32 p-2">
      <img src={Artemislogo} alt="Artemis Logo" class="w-full" />
    </div>

    <button class="ml-auto mr-4 sm:hidden" on:click={toggleMobileMenu}>
      <svg
        xmlns="http://www.w3.org/2000/svg"
        fill="none"
        viewBox="0 0 24 24"
        stroke-width="1.5"
        stroke="currentColor"
        class="w-6 h-6"
      >
        <path
          stroke-linecap="round"
          stroke-linejoin="round"
          d="M3.75 6h16.5M3.75 12h16.5m-16.5 6h16.5"
        />
      </svg>
    </button>

    <div class={`sm:mr-[31vw] sm:block ${mobileMenuOpen ? "block" : "hidden"}`}>
      <ul class="flex flex-col sm:flex-row pt-4 text-xl font-bold">
        {#each headerItems as { page, location }}
          <li
            class="bg-myHeaderButton border-black border-2 border-solid rounded-3xl mx-4 my-2 sm:my-0 p-4"
          >
            <a href={`/${location}`}>{page}</a>
          </li>
        {/each}
      </ul>
    </div>
  </div>
</header>
