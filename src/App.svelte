<script lang="ts">
  import StepEdit from "./components/StepEdit.svelte";
  import StepUpload from "./components/StepUpload.svelte";
  import Foot from "./pages/Foot.svelte";
  import Header from "./pages/Header.svelte";
  import { imageStatus } from "./store";
  import { ImageStatus } from "./types.d";
</script>

<div>
  <Header />
  <main class="my-20">
    <p class="text-white text-center my-5">
      A Svelte app built on top Cloudinary AI APIs to remove background from images
    </p>
    <div class="flex flex-col justify-center items-center my-10">
      {#if $imageStatus === ImageStatus.READY || $imageStatus === ImageStatus.UPLOADING}
        <StepUpload />
      {:else if $imageStatus === ImageStatus.DONE}
        <StepEdit />
      {/if}
    </div>
  </main>
  <Foot />
</div>
