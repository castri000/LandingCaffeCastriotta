<script lang="ts">
  const { title = 'titolo', videoUrl = '' } = $props<{
    title?: string;
    videoUrl?: string;
  }>();
</script>

<div class="header">
  <div class="header-content">
    <div class="video-container">
    <h1 class="header-title">{title}</h1>
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
    padding: var(--spacing-7) var(--spacing-10);
    width: 100%;
    box-sizing: border-box;
    min-height: 400px;
  }

  .header-content {
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: var(--spacing-7);
    width: 100%;
  }

  .header-title {
    font-family: var(--font-primary);
    font-weight: 700;
    font-size: var(--unit-80);
    color: var(--color-content-primary);
    text-align: center;
    margin: 0;
    line-height: 1;
    white-space: nowrap;
  }

  .video-container {
    width: 100%;
    max-width: 100%;
    aspect-ratio: 16 / 9;
    border-radius: var(--radius-xl);
    overflow: hidden;
    background: var(--brand-800);
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
</style>
