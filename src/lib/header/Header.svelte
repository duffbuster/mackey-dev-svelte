<script lang="ts">
  import { onMount } from 'svelte';

  import logo from './mackeydev_FullColor.svg';

  // fucking typescript man
  let about: any;
  let skills: any;
  let testimonials: any;

  let activeNavItem: 'about' | 'skills' | 'testimonials';

  const handleResumeClick = () => {
    console.log('resume click');
  };

  const setActiveNav = (currentScroll: number) => {
    if (currentScroll <= about.offsetTop && currentScroll < skills.offsetTop) {
      activeNavItem = 'about';
    } else if (currentScroll <= skills.offsetTop && currentScroll < testimonials.offsetTop) {
      activeNavItem = 'skills';
    } else if (currentScroll <= testimonials.offsetTop) {
      activeNavItem = 'testimonials';
    }
  };

  let lastScroll = 0;
  let headerVisible = true;
  onMount(() => {
    about = document.getElementById('about');
    skills = document.getElementById('skills');
    testimonials = document.getElementById('testimonials');

    setActiveNav(window.scrollY);

    const onScroll = () => {
      const currentScroll = window.scrollY;

      if (currentScroll > lastScroll + 20) {
        headerVisible = false;
      } else if (currentScroll < lastScroll) {
        headerVisible = true;
      }

      setActiveNav(currentScroll);

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
        <a class:active={activeNavItem === 'about'} href="#about">About</a>
      </li>
      <li>
        <a class:active={activeNavItem === 'skills'} href="#skills">Skills</a>
      </li>
      <li>
        <a class:active={activeNavItem === 'testimonials'} href="#testimonials">Testimonials</a>
      </li>
      <li>
        <button on:click={handleResumeClick}>Resume</button>
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

  nav a {
    border-bottom: 0px solid var(--orange);
    color: var(--navy);
    font-size: 18px;
    font-weight: bold;
    line-height: 1.5;
    letter-spacing: 0.05em;
    margin-right: calc(var(--spacing-unit) * 4);
    text-decoration: none;
    text-transform: uppercase;
    transition: border ease-in 0.2s;
  }

  nav a.active {
    border-bottom-width: 2px;
  }

  nav a:hover {
    border-bottom-width: 2px;
  }
</style>
