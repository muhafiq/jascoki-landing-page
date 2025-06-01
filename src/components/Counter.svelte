<script>
  import { onMount } from "svelte";

  let count = 0;
  export let target;
  const duration = 4000;

  export let plus = false;
  let finished = false;

  onMount(() => {
    const start = performance.now();

    const update = (now) => {
      const elapsed = now - start;
      const progress = Math.min(elapsed / duration, 1);
      count = Math.floor(progress * target);

      if (progress < 1) {
        requestAnimationFrame(update);
      } else {
        count = target;
        finished = true;
      }
    };

    requestAnimationFrame(update);
  });
</script>

<p class="text-5xl md:text-7xl font-bold text-primary tracking-wide">
  {count}{plus && finished ? "+" : null}
</p>
