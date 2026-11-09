<script>
  let { go } = $props();
</script>

<section class="hero-screen" id="home">
  <div class="hero-copy">
    <div class="system-kicker">PORTFOLIO.EXE / VERSION 1.0</div>
    <h1>Hi, I’m<br /><span>Tshepiso.</span></h1>
    <h2>SOFTWARE ENGINEER<br />BACKEND &amp; CLOUD ENTHUSIAST</h2>
    <p>
      I turn ideas into systems that work. From backend services and cloud
      infrastructure to AI-powered applications, I build technology that solves
      real problems.
    </p>
    <div class="hero-buttons">
      <button class="win-button primary-win" onclick={() => go('projects')}>
        Explore My Work
        <svg viewBox="0 0 16 16" aria-hidden="true">
          <path
            d="M2 8h10M8 4l4 4-4 4"
            fill="none"
            stroke="currentColor"
            stroke-width="1.5"
          />
        </svg>
      </button>
      <button class="win-button" onclick={() => go('contact')}>Let’s Connect</button>
    </div>
  </div>
  <div class="hero-portrait">
    <div class="portrait-title">T.TLHONG.JPG</div>
    <img
      src="assests/Tshepiso blaxck and white piture.svg"
      alt="Portrait placeholder for Tshepiso Tlhong"
    />
    <div class="portrait-status">
      640 × 800 pixels <span>PLACEHOLDER</span>
    </div>
  </div>
  <div class="hero-status">
    <span><i></i> SYSTEM STATUS: READY</span>
    <span>BASED IN SOUTH AFRICA</span>
    <span>ALWAYS BUILDING</span>
  </div>
</section>
