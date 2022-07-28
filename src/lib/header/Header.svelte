<script lang="ts">
  import { onMount } from 'svelte';

  import logo from './mackeydev_FullColor.svg';

  const handleClick = (target: string) => {
    console.log('Click!', target);
  };

  let lastScroll = 0;
  let headerVisible = true;
  onMount(() => {
    const onScroll = () => {
      const currentScroll = window.scrollY;

      if (currentScroll > lastScroll) {
        headerVisible = false;
      } else if (currentScroll < lastScroll) {
        headerVisible = true;
      }

      lastScroll = currentScroll;
    };

    window.addEventListener('scroll', onScroll);
    return () => window.removeEventListener('scroll', onScroll);
  });
</script>

<header class:visible={headerVisible}>
  <div class="brand">
    <a href="#hero">
      <img src={logo} alt="MackeyDev" />
    </a>
  </div>

  <nav>
    <ul>
      <li>
        <a on:click={() => handleClick('about')} href="#about">About</a>
      </li>
      <li>
        <a on:click={() => handleClick('skills')} href="#skills">Skills</a>
      </li>
      <li>
        <a on:click={() => handleClick('testimonials')} href="#testimonials">Testimonials</a>
      </li>
      <li>
        <button on:click={() => handleClick('resume')}>Resume</button>
      </li>
    </ul>
  </nav>
</header>

<style>
  header {
    align-items: center;
    background-color: var(--pure-white);
    box-sizing: border-box;
    display: flex;
    justify-content: space-between;
    padding: 24px 64px;
    position: fixed;
    top: -100px;
    transition: top ease-in-out 0.3s;
    width: 100vw;
  }

  header.visible {
    top: 0;
  }

  .brand {
    width: 269px;
  }

  .brand a {
    display: flex;
    align-items: center;
    justify-content: center;
    width: 100%;
    height: 100%;
  }

  .brand img {
    object-fit: contain;
  }

  nav {
    display: flex;
    justify-content: center;
  }

  ul {
    padding: 0;
    margin: 0;
    display: flex;
    justify-content: center;
    align-items: center;
    list-style: none;
  }

  li {
    align-items: center;
    display: flex;
    position: relative;
    height: 100%;
  }

  li.active::before {
  }

  nav a {
    color: var(--navy);
    font-size: 18px;
    font-weight: bold;
    line-height: 1.5;
    letter-spacing: 0.05em;
    margin-right: calc(var(--spacing-unit) * 4);
    text-decoration: none;
    text-transform: uppercase;
  }

  a:hover {
  }
</style>
