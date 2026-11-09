<script>
  let { type = 'folder', paper = false } = $props();
</script>

{#if type === 'computer'}
  <span class="pixel-icon computer-icon" aria-hidden="true"><i></i><b></b></span>
{:else if type === 'mail'}
  <span class="pixel-icon mail-icon" aria-hidden="true"><i></i></span>
{:else}
  <span class="pixel-icon folder-icon {paper ? 'with-paper' : ''}" aria-hidden="true"><i></i></span>
{/if}
