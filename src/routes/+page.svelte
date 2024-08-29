<script lang="ts">
  import { shareText } from "tauri-plugin-sharesheet";

  let text = "This is shared text";
  let mimeType: string = "text/plain";


  async function share() {
    shareText(text, {mimeType});
  }
</script>

<div class="container">
  <h1>Tauri Sharesheet Demo</h1>

  <form class="row" on:submit|preventDefault={share}>
    <div>Text: <input bind:value={text} /></div>
    <div>Mime Type (Android Only): <input bind:value={mimeType} /></div>

    <button type="submit">Share</button>
  </form>
</div>
