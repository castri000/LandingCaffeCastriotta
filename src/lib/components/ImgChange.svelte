<script lang="ts">
  const { imageUrl = '', alt = '' } = $props<{
    imageUrl?: string;
    alt?: string;
  }>();
</script>

<div class="img-change">
  {#if imageUrl}
    <img src={imageUrl} {alt} class="gallery-image" />
  {/if}
</div>

<style>
  .img-change {
    position: relative;
    width: 368px;
    height: 480px;
    border-radius: var(--radius-xl);
    overflow: hidden;
    background: var(--brand-600);
  }

  .gallery-image {
    width: 100%;
    height: 100%;
    object-fit: cover;
    border-radius: var(--radius-xl);
    display: block;
  }
</style>
