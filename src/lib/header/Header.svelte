<script lang="ts">
  import { onMount } from 'svelte';

  import desktopLogo from './mackeydev_FullColor.svg';
  import hamburgerIcon from './Hamburger_icon.svg';
  import mobileLogo from './mackeydev_mobile.svg';

  // fucking typescript man
  let about: any;
  let skills: any;
  let testimonials: any;

  let activeNavItem: 'about' | 'skills' | 'testimonials';

  let hamburgerMenuOpen = false;

  const handleResumeClick = () => {
    window.open('https://mackey-resume.s3.amazonaws.com/Colin+Mackey+Resume.pdf', 'blank');
  };

  const handleHamburgerMenuClick = () => {
    hamburgerMenuOpen = !hamburgerMenuOpen;
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
        hamburgerMenuOpen = false;
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

<!-- NOTE: I might be able to fix the mobile menu overflow by 
  wrapping the interior of the header and styling that -->
<!-- That won't fix the animation on reload though, might be able to use animate css if the above works... -->
<header class:visible={headerVisible}>
  <div class="brand">
    <a href="#hero">
      <img class="desktop-logo" src={desktopLogo} alt="MackeyDev" />
      <img class="mobile-logo" src={mobileLogo} alt="MackeyDev" />
    </a>
  </div>

  <nav class:closed={!hamburgerMenuOpen} class:open={hamburgerMenuOpen}>
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

  <div on:click={handleHamburgerMenuClick} class="hamburger-menu" class:open={hamburgerMenuOpen}>
    <img src={hamburgerIcon} alt="Menu" />
  </div>
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
    transition: border ease 0.2s;
  }

  nav a.active {
    border-bottom-width: 2px;
  }

  nav a:hover {
    border-bottom-width: 2px;
    border-color: var(--orange-lite);
  }

  .hamburger-menu {
    display: none;
  }

  .desktop-logo {
    display: block;
  }
  .mobile-logo {
    display: none;
  }

  @keyframes mobileNavOpen {
    0% {
      opacity: 0;
      max-height: 0px;
    }
    100% {
      opacity: 1;
      max-height: 300px;
    }
  }

  @keyframes mobileNavClose {
    0% {
      opacity: 1;
      max-height: 300px;
    }
    100% {
      opacity: 0;
      max-height: 0px;
    }
  }

  /* Tablet */
  @media screen and (max-width: 992px) {
    header {
      padding: 18px 24px;
    }

    .hamburger-menu {
      display: flex;
      cursor: pointer;
    }

    nav {
      max-height: 0;
    }

    /* TODO: Fix this animation */
    nav.closed {
      animation-duration: 0.3s;
      animation-fill-mode: both;
      animation-name: mobileNavClose;
      animation-timing-function: ease-in;
    }

    nav.open {
      animation-duration: 0.3s;
      animation-fill-mode: both;
      animation-name: mobileNavOpen;
      animation-timing-function: ease-in;
    }

    nav {
      animation-fill-mode: both;
      background-color: white;
      box-sizing: border-box;
      justify-content: flex-end;
      left: 0;
      padding: 24px;
      position: absolute;
      top: 70px;
      width: 100%;
    }

    nav ul {
      align-items: flex-end;
      flex-direction: column;
    }

    nav li a {
      margin-bottom: 16px;
      margin-right: 0;
    }

    .desktop-logo {
      display: none;
    }
    .mobile-logo {
      display: block;
    }

    .brand {
      width: 100px;
    }

    .brand a {
      justify-content: flex-start;
    }

    .brand img {
      width: 100px;
    }
  }
</style>
