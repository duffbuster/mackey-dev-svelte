<div class="skills" id="skills">
  <div class="skills-quadrant">
    <h1>Work Experience</h1>
    <ul>
      <li>
        <p class="skills-copy">
          I work at Penn Entertainment as a Senior Front-End Engineer, where I help build and
          maintain the web presence for ESPN Bet and theScore Bet. I help maintain and develop vital
          parts of our application, ensuring we deliver a consistent user experience and stay in
          compliance with local laws.
        </p>
      </li>
      <li>
        <p class="skills-copy">
          Previously, I spent 6 years consulting for different companies, building a resume of
          clients that includes Fortune 500 companies, non-profits, and small startups. My
          experience consulting taught me how to communicate with empathy, and how to work with
          people to build the best solution to fit their needs.
        </p>
      </li>
    </ul>
  </div>
  <div class="skills--quadrant">
    <h1>Technical Skills</h1>
    <ul>
      <li>
        <p class="skills-copy">
          I have experience working with most major Javascript front-end frameworks. I've built apps
          from scratch using React, contributed to enterprise-level deployments of Angular, and
          worked with Vue developing Barstool Sportsbook.
        </p>
      </li>
      <li>
        <p class="skills-copy">
          I've used Webflow to develop websites for clients, and have experience building responsive
          designs with Figma.
        </p>
      </li>
      <li>
        <p class="skills-copy">
          My DevOps skills include experience with AWS, building infrastructure for cloud
          applications and distributed websites. I've worked with Docker to build modular
          applications, and deployed static sites with AWS S3 and CloudFront.
        </p>
      </li>
    </ul>
  </div>
  <div class="skills--quadrant">
    <div class="cat-mask"></div>
  </div>
  <div class="skills--quadrant">
    <h1>Soft Skills</h1>
    <ul>
      <li>
        <p class="skills-copy">
          My experience as a consultant helped me grow communication skills that are useful outside
          of the consulting world. Being able to listen with empathy and communicate ideas in a
          consistent manner are essential parts of software engineering.
        </p>
      </li>
      <li>
        <p class="skills-copy">
          As a Senior Engineer, I help mentor junior developers and interns. I enjoy helping others
          grow their skills, and work through issues they encounter.
        </p>
      </li>
      <li>
        <p class="skills-copy">
          I have experience working on teams with different software development methodologies. I've
          worked with Agile, Scrum, and Kanban, and have stepped in to run lifecycle meetings when
          needed.
        </p>
      </li>
    </ul>
  </div>
</div>

<style>
  .skills {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: calc(var(--spacing-unit) * 4);
    grid-template-rows: 1fr 1fr;
    max-width: 1600px;
    padding: calc(var(--spacing-unit) * 8);
  }

  .skills-quadrant {
    padding-right: calc(var(--spacing-unit) * 5);
  }

  .skills ul {
    list-style: none;
    padding: 0 0 0 calc(var(--spacing-unit) * 2);
    margin-top: calc(var(--spacing-unit) * 4);
  }

  .skills-copy {
    margin-bottom: 0;
    margin-left: calc(var(--spacing-unit) * 2);
  }

  .skills ul li {
    background: url('/Vector.svg') no-repeat;
    background-position-y: 3px;
    list-style-type: none;
    margin: 0;
    margin-bottom: calc(var(--spacing-unit) * 3);
    padding: 0px 0px 1px 24px;
    vertical-align: middle;
  }

  .cat-mask {
    background-image: url('/lady.JPG');
    background-size: cover;
    background-position-y: 40%;
    border-radius: 12px;
    height: 443px;
    margin: 0 auto;
    max-width: 100%;
    width: 431px;
  }

  /* Tablet */
  @media screen and (max-width: 992px) {
    .skills {
      gap: calc(var(--spacing-unit) * 2);
      padding: calc(var(--spacing-unit) * 4);
    }

    .cat-mask {
      height: 350px;
      width: 350px;
    }
  }

  /* Mobile */
  @media screen and (max-width: 479px) {
    .cat-mask {
      height: 300px;
      width: 300px;
    }
    .skills {
      grid-template-columns: 1fr;
    }

    .skills ul {
      margin-top: calc(var(--spacing-unit) * 2);
    }

    .skills ul li {
      background-position-y: 5px;
      background-size: 16px;
      padding-left: 12px;
    }

    .skills-quadrant {
      padding: 0;
    }
  }
</style>
