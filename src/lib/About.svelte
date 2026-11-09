<script>
  import Window from './Window.svelte';
  import Pixel from './Pixel.svelte';

  const interests = [
    'Photography',
    'Rugby',
    'Technology communities',
    'Hackathons',
    'Continuous learning'
  ];
</script>

<Window id="about" title="About Me — NOTEPAD">
  <div class="notepad-menu">File&nbsp;&nbsp; Edit&nbsp;&nbsp; Search&nbsp;&nbsp; Help</div>
  <div class="notepad-page">
    <p class="file-heading">ABOUT_ME.TXT</p>
    <h2>More than just writing code.</h2>
    <p>
      I’m a software engineering student and developer who enjoys understanding
      how technology works beneath the surface.
    </p>
    <p>
      My journey has been driven by curiosity, self-learning and the desire to
      build things that solve actual problems. Through ALX, WeThinkCode,
      independent projects and hackathons, I’ve developed experience across
      backend systems, APIs, databases, cloud infrastructure and AI-powered
      applications.
    </p>
    <p>
      I’m particularly interested in backend engineering and cloud
      computing—designing systems that are reliable, scalable and useful.
    </p>
    <div class="quote-box">
      “The best engineers aren’t just people who know how to code. They’re
      people who know how to think, adapt and build.”
    </div>
    <h3>BEYOND THE TERMINAL</h3>
    <div class="interest-grid">
      {#each interests as interest (interest)}
        <span><Pixel type="folder" /> {interest}</span>
      {/each}
    </div>
  </div>
</Window>
