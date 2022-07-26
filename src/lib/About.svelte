<div class="about">
  <div class="column-1">
    <div class="about-copy">
      <h1 class="display-76">I write code.</h1>
      <p>
        I'm a technology-minded front-end developer with an eye for design and a passion for User
        Experience. I've built experience on startup teams, consulted at Fortune 500 companies, and
        hacked my way through my own freelance engagements.
      </p>
      <button>Learn More</button>
    </div>
  </div>

  <div class="column-2">
    <div class="headshot" />
  </div>
</div>

<style>
  /* Desktop Styles */
  .about {
    display: grid;
    grid-template-columns: 1fr 1fr;
    padding: 0 64px;
  }

  .about-copy {
    align-items: flex-start;
    display: flex;
    flex-direction: column;
    justify-content: center;
    height: 100%;
    padding-left: 104px;
  }

  .about-copy p {
    max-width: 547px;
  }

  .headshot {
    background-image: url('/headshot.JPEG');
    background-position-y: 50%;
    background-size: cover;
    border-radius: 50%;
    height: 572px;
    margin: 124px auto;
    width: 572px;
  }
</style>
