<script lang="ts">
  const { title = 'titolo', videoUrl = '' } = $props<{
    title?: string;
    videoUrl?: string;
  }>();
</script>

<div class="header">
  <div class="header-content">
    <h1 class="header-title">{title}</h1>
    <div class="video-container">
      {#if videoUrl}
        <video controls class="video-player">
          <source src={videoUrl} type="video/mp4" />
          Il tuo browser non supporta il tag video.
        </video>
      {/if}
    </div>
  </div>
</div>

<style>
  .header {
    display: flex;
    align-items: center;
    justify-content: center;
    padding: var(--spacing-7) var(--spacing-7);
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
    max-width: 1200px;
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

  .video-placeholder {
    width: 100%;
    height: 100%;
    display: flex;
    align-items: center;
    justify-content: center;
    background: linear-gradient(135deg, var(--brand-800) 0%, #6b4329 100%);
  }

  .play-icon {
    width: 80px;
    height: 80px;
    color: var(--brand-600);
    opacity: 0.7;
  }

  .video-player {
    width: 100%;
    height: 100%;
    object-fit: cover;
  }
</style>
