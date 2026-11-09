<script>
  let { id, title, children } = $props();
</script>

<section class="content-window" {id}>
  <div class="sub-titlebar">
    <span class="mini-app-icon"></span>
    <strong>{title}</strong>
    <span class="sub-controls">
      <i>_</i>
      <i>□</i>
      <i>×</i>
    </span>
  </div>
  <div class="window-body">
    {@render children?.()}
  </div>
</section>
