<script lang="ts">
  const { heading = '', subheading = '', description = '', imageUrl = '' } = $props<{
    heading?: string;
    subheading?: string;
    description?: string;
    imageUrl?: string;
  }>();
</script>

<section class="text-image-section">
  <div class="text-content">
    <h2 class="section-heading">{heading}</h2>
    <h3 class="section-subheading">{subheading}</h3>
    <p class="section-description">{description}</p>
  </div>
  <div class="image-content">
    {#if imageUrl}
      <img src={imageUrl} alt={heading} class="section-image" />
    {/if}
  </div>
</section>

<style>
  .text-image-section {
    display: flex;
    gap: var(--spacing/7);
    align-items: center;
    justify-content: center;
    padding: var(--unit/80) var(--spacing/10);
    width: 100%;
    box-sizing: border-box;
  }

  .text-content {
    flex: 0 0 auto;
    width: 748px;
    display: flex;
    flex-direction: column;
    gap: var(--spacing/6);
    justify-content: center;
  }

  .section-heading {
    font-family: var(--font-primary);
    font-weight: 700;
    font-size: var(--unit/72);
    color: white;
    margin: 0;
    line-height: 1.2;
  }

  .section-subheading {
    font-family: var(--font-primary);
    font-weight: 500;
    font-size: var(--unit/48);
    color: white;
    margin: 0;
    line-height: 1.2;
  }

  .section-description {
    font-family: var(--font-primary);
    font-weight: 400;
    font-size: 24px;
    color: white;
    line-height: 1.6;
    text-align: justify;
    margin: 0;
    max-width: 704px;
  }

  .image-content {
    flex: 0 0 auto;
    width: 368px;
    height: 480px;
  }

  .section-image {
    width: 100%;
    height: 100%;
    object-fit: cover;
    border-radius: var(--radius-xl);
    display: block;
  }
</style>
