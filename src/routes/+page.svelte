<script lang="ts">
  import { invoke } from "@tauri-apps/api/tauri";
  import shared from "../lib/shared";

  let name = "";
  let greetMsg = "";

  async function greet() {
    // Learn more about Tauri commands at https://tauri.app/v1/guides/features/command
    greetMsg = await invoke("greet", { name });
  }
</script>

<div>
  <title>{shared.immutable.CONSTS.APP_NAME}</title>
  hello!
</div>

<style>
</style>
