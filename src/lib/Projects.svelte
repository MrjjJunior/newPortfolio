<script>
  import Window from './Window.svelte';
  import Pixel from './Pixel.svelte';
  import { TRACKER_ROWS } from './data.js';

  const tech = [
    'FastAPI backend',
    'React frontend',
    'PostgreSQL',
    'AWS EC2',
    'AWS RDS',
    'Private networking',
    'AI skill matching'
  ];
</script>

<Window id="projects" title="Job Application Tracker — FEATURED PROJECT">
  <div class="project-window">
    <div class="project-heading">
      <div>
        <span class="dos-path">C:\PROJECTS\JOB_TRACKER\</span>
        <h2>Job Application<br />Tracker</h2>
      </div>
      <span class="project-stamp">PROJECT 01<br /><b>FEATURED</b></span>
    </div>
    <div class="project-preview">
      <div class="preview-titlebar">Trackr — Applications Dashboard</div>
      <div class="tracker-app">
        <aside>
          <b>TRACKR</b>
          <span class="selected">Dashboard</span>
          <span>Applications</span>
          <span>Skill Analysis</span>
          <span>Settings</span>
        </aside>
        <div class="tracker-main">
          <h4>APPLICATIONS OVERVIEW</h4>
          <div class="tracker-stats">
            <b>18<small>ACTIVE</small></b>
            <b>05<small>INTERVIEWS</small></b>
            <b>72%<small>AVG MATCH</small></b>
          </div>
          {#each TRACKER_ROWS as row (row.company)}
            <div class="tracker-row">
              <i>{row.company[0]}</i>
              <p>
                <b>{row.role}</b>
                <small>{row.company}</small>
              </p>
              <em>{row.status}</em>
              <strong>{row.match}</strong>
            </div>
          {/each}
        </div>
      </div>
    </div>
    <div class="project-details">
      <p>
        An application management platform designed to help job seekers organise
        applications, monitor progress and identify skill gaps between their
        capabilities and job requirements.
      </p>
      <p>
        I built it to solve a problem I experienced myself: keeping track of
        multiple applications while understanding how well my skills matched
        each opportunity.
      </p>
      <div class="tech-list">
        {#each tech as item (item)}
          <span>✓ {item}</span>
        {/each}
      </div>
      <button class="win-button project-button">Case study available on request</button>
    </div>
  </div>
</Window>
