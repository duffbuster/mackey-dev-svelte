<script lang="ts">
  import Header from '$lib/header/Header.svelte';
  import Footer from '$lib/footer/Footer.svelte';

  import '../styles/app.css';
</script>

<div class="animate__animated animate__fadeIn">
  <Header />

  <slot />

  <Footer />
</div>
