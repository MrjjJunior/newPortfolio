<script>
  import Window from './Window.svelte';
  import Pixel from './Pixel.svelte';
  import { SKILLS } from './data.js';
</script>

<Window id="skills" title="My Arsenal — C:\TOOLS">
  <div class="folder-view">
    {#each SKILLS as group, i (group.title)}
      <article class="skill-folder">
        <div class="skill-folder-head">
          <Pixel type="folder" paper />
          <h3>{group.title}</h3>
          <span>{String(i + 1).padStart(2, '0')}</span>
        </div>
        <div class="skill-files">
          {#each group.items as item, j (item)}
            <span class={j < 3 ? 'core-skill' : ''}>
              <i class="file-icon">A</i>{item}
            </span>
          {/each}
        </div>
      </article>
    {/each}
  </div>
  <div class="folder-status">
    5 object(s)&nbsp; | &nbsp;Core technologies are highlighted in blue
  </div>
</Window>
