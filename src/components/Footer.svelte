<!-- src/components/Footer.svelte -->
<script>
  import { Mail, Instagram, Twitter } from "@lucide/svelte";
</script>

<footer class="bg-base-1/60 backdrop-blur-md px-6 md:px-16 py-10 relative">
  <img
    src="/overlay.svg"
    alt="overlay footer"
    class="absolute w-full left-0 bottom-0 z-10"
  />
  <div
    class="max-w-7xl mx-auto flex flex-col md:flex-row justify-between items-start gap-10 relative z-20"
  >
    <!-- Left -->
    <div class="flex flex-col items-start gap-4">
      <img src="/logo.png" alt="Logo" class="w-24 h-24 mb-4" />
      <div class="flex gap-4 mt-2 text-gray-700">
        <a href="/#" aria-label="Email"
          ><Mail class="w-8 h-8 hover:text-primary duration-300" /></a
        >
        <a href="/#" aria-label="Instagram"
          ><Instagram class="w-8 h-8 hover:text-primary duration-300" /></a
        >
        <a href="/#" aria-label="Twitter"
          ><Twitter class="w-8 h-8 hover:text-primary duration-300" /></a
        >
      </div>
    </div>

    <!-- Right -->
    <div>
      <h2 class="font-bold text-lg mb-2">Quick Links</h2>
      <ul class="space-y-1 text-gray-700">
        <li><a href="/#" class="hover:text-primary duration-300">Home</a></li>
        <li>
          <a href="/#services" class="hover:text-primary duration-300"
            >Layanan</a
          >
        </li>
        <li>
          <a href="/#order-now" class="hover:text-primary duration-300"
            >Kontak</a
          >
        </li>
      </ul>
    </div>
  </div>
</footer>
