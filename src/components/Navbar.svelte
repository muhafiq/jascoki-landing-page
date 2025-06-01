<script>
  import {
    Menu,
    Home,
    HandHeart,
    PhoneCall,
    MessageCircle,
  } from "@lucide/svelte";
  import { fly } from "svelte/transition";
  import { quintOut, quintIn } from "svelte/easing";

  let isMobileMenuOpen = false;

  const menus = [
    { name: "Home", href: "/#", icon: Home },
    { name: "Layanan", href: "/#services", icon: HandHeart },
    { name: "Kontak", href: "/#order-now", icon: PhoneCall },
  ];

  // Fungsi untuk toggle menu mobile
  function toggleMobileMenu() {
    isMobileMenuOpen = !isMobileMenuOpen;
  }
</script>

<header
  class="flex px-8 py-4 text-base-1 justify-between items-center w-full max-h-32 bg-accent/50 fixed z-20"
>
  <a href="/#">
    <img src="/logo.png" alt="Jascoki Logo" class="w-12 select-none md:w-14" />
  </a>

  <nav class="items-center gap-6 font-medium hidden md:flex">
    {#each menus as menu}
      <a href={menu.href} class="hover:text-primary duration-500">{menu.name}</a
      >
    {/each}
  </nav>

  <button
    class="px-4 py-2 rounded-md bg-base-1 text-accent shadow text-xs md:text-base"
    >Kode Promo: <span class="text-red-500 font-bold">MERDEKA</span>
  </button>

  <button
    on:click={toggleMobileMenu}
    class="md:hidden p-2 z-20 text-base-1"
    aria-label="Toggle menu"
    aria-expanded={isMobileMenuOpen}
  >
    <Menu class="w-8 h-8" />
  </button>

  {#if isMobileMenuOpen}
    <nav
      class="absolute w-full px-4 py-4 left-0 top-full bg-accent/50 flex flex-col gap-2 md:hidden z-10 shadow-lg"
      in:fly={{ y: -50, duration: 300, easing: quintOut }}
      out:fly={{ y: -50, duration: 300, easing: quintIn }}
    >
      {#each menus as menu}
        <li
          class="list-none flex items-center gap-2 rounded-md duration-100 p-4"
        >
          <svelte:component this={menu.icon} size={24} class="text-base-1" />
          <a href={menu.href} class="text-base-1 hover:text-accent duration-500"
            >{menu.name}</a
          >
        </li>
      {/each}
      <li
        class="self-center bg-primary w-full justify-center list-none flex items-center gap-2 rounded-md duration-100 p-4"
      >
        <MessageCircle size={24} class="text-base-1" />
        <a href="/#" class="text-base-1 hover:text-accent">Pesan Sekarang</a>
      </li>
    </nav>
  {/if}
</header>
