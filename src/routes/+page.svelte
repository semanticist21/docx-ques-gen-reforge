<script lang="ts">
  import shared from "$lib/shared";
  import mammoth from "mammoth";
  import { writable } from "svelte/store";

  const htmlContent = writable<string>("");

  const test = async () => {
    const file = await fetch("/example.docx");
    const arrayBuffer = await file.arrayBuffer();

    const result = await mammoth.convertToHtml({ arrayBuffer });
    htmlContent.set(result.value); 
  };

  test();
</script>

<div>
  <title>{shared.immutable.CONSTS.APP_NAME}</title>
    {@html $htmlContent}
    <td>asdasd</td>
</div>

<style>
  :global(td) {
    border: 1px solid #000;
  }
</style>
