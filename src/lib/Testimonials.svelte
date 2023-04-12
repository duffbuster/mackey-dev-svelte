<script lang="ts">
  import { testimonials } from './assets/testimonials';
</script>

<div class="testimonials" id="testimonials">
  <div class="testimonials-header">
    <h1>Testimonials</h1>
    <p>
      I've done a lot of great work for freelance clients as well. Don't just take my word for it
      though...
    </p>
  </div>

  <div class="testimonials-grid">
    {#each testimonials as testimonial}
      <div class="testimonials-grid-item">
        <h2>{testimonial.title}</h2>
        <p>
          {testimonial.body}
        </p>
        <a href={testimonial.link} target="_blank" rel="noopener noreferrer">
          <img src={testimonial.logo} alt={testimonial.alt} />
        </a>
      </div>
    {/each}
  </div>
</div>

<style>
  .testimonials {
    margin: 0 auto;
    max-width: 1262px;
    padding: calc(var(--spacing-unit) * 10) 0;
  }

  .testimonials-header {
    align-items: center;
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    margin-bottom: calc(var(--spacing-unit) * 8);
  }

  .testimonials-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: calc(var(--spacing-unit) * 8);
  }

  .testimonials-grid-item {
    padding-right: calc(var(--spacing-unit) * 8);
  }

  .testimonials-grid-item img {
    margin-top: calc(var(--spacing-unit) * 2);
    max-width: 250px;
  }

  /* Tablet */
  @media screen and (max-width: 992px) {
    .testimonials {
      padding: 0 48px 24px;
    }

    .testimonials-grid {
      gap: calc(var(--spacing-unit) * 4);
    }
  }

  /* Mobile */
  @media screen and (max-width: 479px) {
    .testimonials {
      padding: 24px 16px 48px;
    }

    .testimonials-header {
      margin-bottom: calc(var(--spacing-unit) * 4);
      text-align: center;
    }

    .testimonials-grid {
      grid-template-columns: 1fr;
    }

    .testimonials-grid-item {
      padding-right: 0;
      text-align: center;
    }
  }
</style>
