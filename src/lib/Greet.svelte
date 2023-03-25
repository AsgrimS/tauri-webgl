<script lang="ts">
  import { invoke } from "@tauri-apps/api/tauri";
  import IconFontHand from "~icons/material-symbols/front-hand";

  let name = "";
  let greetMsg = "";

  async function greet() {
    greetMsg = await invoke("greet", { name });
  }
</script>

<div>
  <input class="bg-slate-700" id="greet-input" placeholder="Enter a name..." bind:value={name} />
  <button on:click={greet}>Greet</button>
  <p>{greetMsg}</p>
  <IconFontHand />
</div>
