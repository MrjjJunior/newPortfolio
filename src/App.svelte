<script>
  import { NAV } from './lib/data.js';
  import Pixel from './lib/Pixel.svelte';
  import Hero from './lib/Hero.svelte';
  import About from './lib/About.svelte';
  import Skills from './lib/Skills.svelte';
  import Projects from './lib/Projects.svelte';
  import Experience from './lib/Experience.svelte';
  import Contact from './lib/Contact.svelte';

  let startOpen = $state(false);
  let minimized = $state(false);
  let maximized = $state(false);
  let shutdownOpen = $state(false);
  let clock = $state('');

  function tick() {
    clock = new Intl.DateTimeFormat('en-ZA', {
      hour: '2-digit',
      minute: '2-digit',
      hour12: true
    }).format(new Date());
  }

  $effect(() => {
    tick();
    const interval = window.setInterval(tick, 30000);
    return () => window.clearInterval(interval);
  });

  function go(target) {
    startOpen = false;
    minimized = false;
    window.setTimeout(() => {
      document.getElementById(target)?.scrollIntoView({ behavior: 'smooth' });
    }, 20);
  }
</script>

<main class="desktop">
  <div class="wallpaper-mark" aria-hidden="true">
    <span>TS</span>
    <p>SOFTWARE<br />ENGINEERING</p>
  </div>

  <aside class="desktop-icons" aria-label="Desktop shortcuts">
    {#each NAV.slice(1) as item (item.target)}
      <button class="desktop-shortcut" onclick={() => go(item.target)} ondblclick={() => go(item.target)}>
        <Pixel type={item.icon} />
        <span>{item.label}</span>
      </button>
    {/each}
  </aside>

  {#if !minimized}
    <div class="main-window {maximized ? 'maximized' : ''}">
      <div class="titlebar">
        <div class="titlebar-name">
          <Pixel type="computer" />
          <strong>Tshepiso Tlhong — Portfolio Explorer</strong>
        </div>
        <div class="window-controls">
          <button aria-label="Minimize portfolio window" onclick={() => (minimized = true)}>_</button>
          <button aria-label="Maximize portfolio window" onclick={() => (maximized = !maximized)}>□</button>
          <button aria-label="Close portfolio window" onclick={() => (shutdownOpen = true)}>×</button>
        </div>
      </div>

      <div class="menubar">
        <button><u>F</u>ile</button>
        <button><u>E</u>dit</button>
        <button><u>V</u>iew</button>
        <button><u>G</u>o</button>
        <button><u>H</u>elp</button>
      </div>

      <div class="toolbar">
        <button aria-label="Go back" onclick={() => window.history.back()}>
          ←<small>Back</small>
        </button>
        <button aria-label="Go forward" onclick={() => window.history.forward()}>
          →<small>Forward</small>
        </button>
        <span class="toolbar-rule"></span>
        <button onclick={() => go('home')}>
          <Pixel type="computer" />
          <small>Home</small>
        </button>
        <button onclick={() => go('projects')}>
          <Pixel type="folder" />
          <small>Projects</small>
        </button>
        <div class="address">
          <label>Address</label>
          <div>
            <Pixel type="folder" /> C:\TSHEPISO\PORTFOLIO\INDEX.HTML
          </div>
        </div>
      </div>

      <div class="explorer-layout">
        <aside class="explorer-sidebar">
          <div class="sidebar-brand">
            <span>TT</span>
            <p>PORTFOLIO<br />EXPLORER</p>
          </div>
          <div class="sidebar-panel">
            <h3>Contents</h3>
            {#each NAV as item (item.target)}
              <button onclick={() => go(item.target)}>
                <Pixel type={item.icon} />{item.label}
              </button>
            {/each}
          </div>
          <div class="sidebar-panel details">
            <h3>Details</h3>
            <p><b>Location:</b><br />South Africa</p>
            <p><b>Focus:</b><br />Backend &amp; Cloud</p>
            <p class="online"><i></i> Available for opportunities</p>
          </div>
        </aside>

        <div class="site-content">
          <Hero {go} />
          <About />
          <Skills />
          <Projects />
          <Experience />
          <Contact />
          <footer class="site-footer">
            <span>© 2025 TSHEPISO TLHONG</span>
            <span>DESIGNED AROUND CURIOSITY. BUILT WITH INTENT.</span>
          </footer>
        </div>
      </div>

      <div class="statusbar">
        <span>6 object(s)</span>
        <span>Internet zone</span>
      </div>
    </div>
  {/if}

  {#if shutdownOpen}
    <div class="dialog-backdrop">
      <div class="shutdown-dialog">
        <div class="titlebar">
          <strong>Exit Portfolio</strong>
          <button onclick={() => (shutdownOpen = false)}>×</button>
        </div>
        <div class="shutdown-content">
          <Pixel type="computer" />
          <div>
            <h3>Thanks for stopping by.</h3>
            <p>Would you like to return to the portfolio?</p>
          </div>
        </div>
        <div class="dialog-actions">
          <button class="win-button primary-win" onclick={() => (shutdownOpen = false)}>
            Return
          </button>
          <a class="win-button" href="mailto:?subject=Portfolio%20enquiry">Send a message</a>
        </div>
      </div>
    </div>
  {/if}

  {#if startOpen}
    <div class="start-menu">
      <div class="start-rail">
        <b>Tshepiso</b>
        <span>95</span>
      </div>
      <div class="start-items">
        {#each NAV as item (item.target)}
          <button onclick={() => go(item.target)}>
            <Pixel type={item.icon} />
            <span>{item.label}</span>
          </button>
        {/each}
        <hr />
        <button onclick={() => (shutdownOpen = true)}>
          <span class="shutdown-icon">○</span>
          <span>Shut Down...</span>
        </button>
      </div>
    </div>
  {/if}

  <div class="taskbar">
    <button class="start-button {startOpen ? 'pressed' : ''}" onclick={() => (startOpen = !startOpen)}>
      <span class="start-logo">
        <i></i>
        <i></i>
        <i></i>
        <i></i>
      </span>
      <b>Start</b>
    </button>
    <span class="taskbar-divider"></span>
    <button class="task-app {minimized ? '' : 'active'}" onclick={() => (minimized = false)}>
      <Pixel type="computer" />
      <span>Tshepiso Tlhong — Portfolio</span>
    </button>
    <div class="tray">
      <i class="speaker-icon">◖</i>
      <span>{clock}</span>
    </div>
  </div>
</main>
