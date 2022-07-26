<script lang="ts">
  import facebookLogo from '$lib/assets/f_logo_RGB-Black_72.png';
  import githubLogo from '$lib/assets/GitHub-Mark-120px-plus.png';
  import linkedinLogo from '$lib/assets/iconmonstr-linkedin-3.svg';
  import svelteLogo from '$lib/assets/svelte-logo.svg';
</script>

<footer>
  <div class="footer-content">
    <p class="svelte-block">
      Built with
      <a href="https://kit.svelte.dev/" target="_blank" rel="noopener noreferrer">
        <img class="svelte-logo" src={svelteLogo} alt="Svelte" />
      </a>
    </p>
    <div class="social-block">
      <a href="https://github.com/duffbuster" target="_blank" rel="noopener noreferrer">
        <img src={githubLogo} alt="Github" />
      </a>
      <a href="https://www.linkedin.com/in/mackeydev/" target="_blank" rel="noopener noreferrer">
        <img src={linkedinLogo} alt="LinkedIn" />
      </a>
      <a href="https://www.facebook.com/colinmackeyphoto" target="_blank" rel="noopener noreferrer">
        <img src={facebookLogo} alt="Facebook" />
      </a>
    </div>
  </div>
</footer>

<style>
  footer {
    align-items: center;
    display: flex;
    justify-content: center;
    padding: 32px 0;
  }

  p.svelte-block {
    align-items: center;
    display: flex;
    margin-bottom: calc(var(--spacing-unit) * 2);
  }

  p.svelte-block a {
    align-items: center;
    display: flex;
    margin-left: var(--spacing-unit);
  }

  .svelte-logo {
    width: 32px;
  }

  div.social-block {
    align-items: center;
    display: flex;
    justify-content: space-between;
  }

  div.social-block img {
    width: 32px;
  }
</style>
