<script lang="ts">
  let isHovered = $state(false);

  const { defaultImageUrl = '', hoverImageUrl = '', alt = '' } = $props<{
    defaultImageUrl?: string;
    hoverImageUrl?: string;
    alt?: string;
  }>();
</script>

<div
  class="img-change"
  onmouseenter={() => (isHovered = true)}
  onmouseleave={() => (isHovered = false)}
>
  {#if defaultImageUrl}
    <img
      src={defaultImageUrl}
      {alt}
      class="gallery-image default-image"
      class:hidden={isHovered}
    />
  {/if}
  {#if hoverImageUrl}
    <img
      src={hoverImageUrl}
      alt={`${alt} - Hover`}
      class="gallery-image hover-image"
      class:visible={isHovered}
    />
  {/if}
</div>

<style>
  .img-change {
    position: relative;
    width: 368px;
    height: 480px;
    border-radius: var(--radius-xl);
    overflow: hidden;
  }

  .gallery-image {
    width: 100%;
    height: 100%;
    object-fit: cover;
    border-radius: var(--radius-xl);
    display: block;
    position: absolute;
    inset: 0;
    transition: opacity 0.6s ease;
  }

  .default-image {
    opacity: 1;
    z-index: 1;
  }

  .default-image.hidden {
    opacity: 0;
    z-index: 0;
  }

  .hover-image {
    opacity: 0;
    z-index: 0;
  }

  .hover-image.visible {
    opacity: 1;
    z-index: 1;
  }
</style>
