<script>
  import About from '$lib/About.svelte';
  import Hero from '$lib/Hero.svelte';
  import Skills from '$lib/Skills.svelte';
  import Testimonials from '$lib/Testimonials.svelte';
</script>

<svelte:head>
  <title>MackeyDev</title>
</svelte:head>

<div class="mackeydev">
  <Hero />
  <About />
  <Skills />
  <Testimonials />
</div>

<style>
  .mackeydev {
  }
</style>
