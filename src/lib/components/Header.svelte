<script lang="ts">
  const { videoUrl = '' } = $props<{
    videoUrl?: string;
  }>();
</script>

<div class="header">
  <div class="header-content">
    <div class="video-container">
      {#if videoUrl}
        <video controls class="video-player" src="/videos/video caffe 3.mp4" autoplay muted loop playsinline></video>
      {/if}
    </div>
  </div>
</div>

<style>
  .header {
    display: flex;
    align-items: center;
    justify-content: center;
    padding: var(--spacing-6) var(--spacing-10);
    width: 100%;
    box-sizing: border-box;
    min-height: 200px;
  }

  .header-content {
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: var(--spacing-7);
    width: 100%;
  }

  .video-container {
    width: 100%;
    max-width: 100%;
    aspect-ratio: 16 / 9;
    border-radius: var(--radius-xl);
    overflow: hidden;
    background-color: var(--brand-800);
    display: flex;
    align-items: center;
    justify-content: center;
  }

  .video-player {
    width: 100%;
    height: 100%;
    object-fit: cover;
    pointer-events: none;
  }


  /* Nascondi i controlli del video */
  .video-player::-webkit-media-controls {
  display: none !important;
  }

  .video-player::-webkit-media-controls-enclosure {
  display: none !important;
  }

  .video-player::-webkit-media-controls-panel {
  display: none !important;
  }


  /* RESPONSIVE TABLET */
  @media (max-width: 744px) {

  .header {
    padding: 0 var(--spacing-6);
  }

  .header-content {
    width: 100%;
    max-width: calc(100% - 48px); /* 16px per lato */
    margin: 0 auto;
  }

  .video-container {
    width: 100%;
    border-radius: var(--radius-xl);
  }


}




</style>
