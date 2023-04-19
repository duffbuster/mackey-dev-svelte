<script>
  import About from './lib/About.svelte';
  import Footer from './lib/footer/Footer.svelte';
  import Header from './lib/header/Header.svelte';
  import Hero from './lib/Hero.svelte';
  import Skills from './lib/Skills.svelte';
  import Testimonials from './lib/Testimonials.svelte';
</script>

<svelte:head>
  <script async src="https://www.googletagmanager.com/gtag/js?id=G-XR0DQDF850"></script>
  <script>
    if (typeof window !== 'undefined' && window) {
      const gaId = 'G-XR0DQDF850';

      window.dataLayer = window.dataLayer || [];

      function gtag() {
        dataLayer.push(arguments);
      }
      gtag('js', new Date());
      gtag('config', gaId);
    }
  </script>
</svelte:head>

<div class="mackeydev animate__animated animate__fadeIn">
  <Header />
  <Hero />
  <About />
  <Skills />
  <Testimonials />
  <Footer />
</div>
