<script lang="ts">
	import { page } from '$app/stores';
  import logo from './mackeydev_FullColor.svg';

  const handleClick = (event: MouseEvent, target: string) => {
    event.preventDefault();
    event.stopPropagation();

    console.log('Click!', target)
  }
</script>

<!-- markup (zero or more items) goes here -->
<header>
  <div class="brand">
    <a href="/">
      <img src="{logo}" alt="MackeyDev">
    </a>
  </div>

  <nav>
    <ul>
      <li>
        <a on:click={e => handleClick(e, 'about')} href="/">About</a>
      </li>
      <li>
        <a on:click={e => handleClick(e, 'skills')} href="/">Skills</a>
      </li>
      <li>
        <a on:click={e => handleClick(e, 'testimonials')} href="/">Testimonials</a>
      </li>
      <li>
        <button>Resume</button>
      </li>
    </ul>
  </nav>
</header>

<style>
	/* styles go here */
  header {
    align-items: center;
    background-color: var(--pure-white);
    display: flex;
    justify-content: space-between;
    padding: 24px 64px;
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

  li.active::before { }

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