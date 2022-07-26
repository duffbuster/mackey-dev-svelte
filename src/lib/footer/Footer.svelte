<script lang="ts">
  import facebookLogo from '$lib/assets/f_logo_RGB-Black_72.png';
  import githubLogo from '$lib/assets/GitHub-Mark-120px-plus.png'
  import linkedinLogo from '$lib/assets/iconmonstr-linkedin-3.svg';
  import svelteLogo from '$lib/assets/svelte-logo.svg';
</script>

<!-- markup (zero or more items) goes here -->
<footer>
  <div class="footer-content">
    <p class="svelte-block">
      Built with <img class="svelte-logo" src="{svelteLogo}" alt="Svelte" />
    </p>
    <div class="social-block">
      <img src="{githubLogo}" alt="Github" />
      <img src="{linkedinLogo}" alt="LinkedIn" />
      <img src="{facebookLogo}" alt="Facebook" />
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

  .svelte-logo {
    margin-left: var(--spacing-unit);
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