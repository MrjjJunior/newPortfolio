<script>
  import Window from './Window.svelte';
  import Pixel from './Pixel.svelte';
</script>

<Window id="contact" title="New Message — INBOX">
  <div class="email-window">
    <div class="email-row">
      <!-- svelte-ignore a11y_label_has_associated_control -->
      <label>To:</label>
      <span>Tshepiso Tlhong</span>
    </div>
    <div class="email-row">
      <!-- svelte-ignore a11y_label_has_associated_control -->
      <label>Subject:</label>
      <span>Let’s build something that works.</span>
    </div>
    <div class="email-body">
      <p>
        Have a software engineering role, project or hard problem worth talking
        about?
      </p>
      <h2>Let’s connect.</h2>
      <a class="win-button primary-win" href="mailto:?subject=Let’s%20build%20something">
        Compose Message
        <Pixel type="mail" />
      </a>
      <small>CONTACT DETAILS AVAILABLE ON REQUEST · SOUTH AFRICA / SAST</small>
    </div>
  </div>
</Window>
