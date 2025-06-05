<script>
  import Router from "svelte-spa-router";
  import Home from "./routes/Home.svelte";

  const routes = {
    "/": Home,
  };

  // Fungsi tracking
  function trackPage(path) {
    if (window.gtag) {
      window.gtag("config", "G-41MDZP8CP3", {
        page_path: path,
      });
    }
  }
</script>

<Router {routes} />
