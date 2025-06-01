<script>
  import Navbar from "./Navbar.svelte";
  import Footer from "./Footer.svelte";
</script>

<div>
  <Navbar />
  <main>
    <slot />
  </main>
  <Footer />
</div>
