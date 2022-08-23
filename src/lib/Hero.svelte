<div class="hero" id="hero">
  <div class="hero-text fade-in-up">
    <h1 class="display-76 white">Hi, I'm Colin.</h1>
    <p class="white">Philadelphia, PA</p>
  </div>
</div>

<style>
  @-webkit-keyframes fadeInUp {
    from {
      opacity: 0;
      -webkit-transform: translate3d(0, 100px, 0);
      transform: translate3d(0, 100px, 0);
    }

    to {
      opacity: 1;
      -webkit-transform: translate3d(0, 0, 0);
      transform: translate3d(0, 0, 0);
    }
  }
  @keyframes fadeInUp {
    from {
      opacity: 0;
      -webkit-transform: translate3d(0, 50px, 0);
      transform: translate3d(0, 50px, 0);
    }

    to {
      opacity: 1;
      -webkit-transform: translate3d(0, 0, 0);
      transform: translate3d(0, 0, 0);
    }
  }
  .fade-in-up {
    -webkit-animation-duration: 0.3s;
    animation-duration: 0.3s;
    -webkit-animation-name: fadeInUp;
    animation-name: fadeInUp;
    -webkit-animation-fill-mode: both;
    animation-fill-mode: both;
    animation-timing-function: ease-in;
    animation-delay: 0.1s;
  }
  .hero {
    background-image: url('/pexels-kelly-4642388.png');
    background-position: center;
    background-repeat: no-repeat;
    background-size: cover;
    margin-top: 100px;
    padding: 300px 0;
  }

  .hero-text {
    margin: auto;
    max-width: 60vw;
  }

  /* Tablet */
  @media screen and (max-width: 992px) {
  }

  /* Mobile */
  @media screen and (max-width: 479px) {
  }
</style>
