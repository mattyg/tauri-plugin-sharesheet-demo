<script lang="ts">
  import { shareText } from "tauri-plugin-sharesheet";

  let text = "This is shared text";
  let title: string | undefined;

  async function share() {
    shareText(text, {title});
  }
</script>

<div class="container">
  <h1>Tauri Sharesheet Demo</h1>

  <form class="row" on:submit|preventDefault={share}>
    <div>Text: <input bind:value={text} /></div>
    <div>Title: <input bind:value={title} /></div>

    <button type="submit">Share</button>
  </form>
</div>
