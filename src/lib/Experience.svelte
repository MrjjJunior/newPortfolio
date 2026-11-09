<script>
  import Window from './Window.svelte';
  import { EXPERIENCE } from './data.js';
</script>

<Window id="experience" title="Experience — TIMELINE.EXE">
  <div class="timeline-app">
    <div class="timeline-header">
      <span>NAME</span>
      <span>TYPE</span>
      <span>STATUS</span>
    </div>
    {#each EXPERIENCE as item, i (item.name)}
      <article>
        <span class="timeline-icon">{i + 1}</span>
        <div>
          <h3>{item.name}</h3>
          <p>{item.type}</p>
        </div>
        <b>{item.status}</b>
      </article>
    {/each}
  </div>
</Window>
