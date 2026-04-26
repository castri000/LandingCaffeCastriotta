<script lang="ts">
  let isFlipped = $state(false);

  const { title = '', subtitle = '', description = '', imageUrl = '' } = $props<{
    title?: string;
    subtitle?: string;
    description?: string;
    imageUrl?: string;
  }>();

  function handleClick() {
    isFlipped = !isFlipped;
  }
</script>

<button class="card" class:flipped={isFlipped} onclick={handleClick}>
  <div class="card-back">
    <div class="card-description">
      <p>{description}</p>
    </div>
  </div>
  <div class="card-front">
    {#if imageUrl}
      <img src={imageUrl} alt={title} class="card-image" />
    {/if}
    <div class="card-content">
      <h3 class="card-label">{title}</h3>
      <h2 class="card-title">{subtitle}</h2>
    </div>
  </div>
</button>

<style>
  .card {
    position: relative;
    width: 664px;
    height: 389px;
    border: none;
    border-radius: var(--radius-xl);
    cursor: pointer;
    background: transparent;
    padding: 0;
    perspective: 1000px;
    transform-style: preserve-3d;
  }

  .card-back {
    position: absolute;
    inset: 0;
    background: var(--brand-800);
    border-radius: var(--radius-xl);
    display: flex;
    align-items: center;
    justify-content: center;
    padding: var(--spacing-10);
    box-sizing: border-box;
    z-index: 1;
    backface-visibility: hidden;
    transform-style: preserve-3d;
    transform: rotateY(180deg);
    transition: transform 1s ease;
  }

  .card.flipped .card-back {
    transform: rotateY(0deg);
  }

  .card-description {
    width: 100%;
    text-align: left;
  }

  .card-description p {
    font-family: var(--font-primary);
    font-weight: 400;
    font-size: var(--unit-24);
    color: var(--color-content-primary);
    line-height: 1.5;
    margin: 0;
  }

  .card-front {
    position: absolute;
    inset: 0;
    background: var(--brand-600);
    border-radius: var(--radius-xl);
    padding: 0;
    box-sizing: border-box;
    z-index: 2;
    backface-visibility: hidden;
    transform-style: preserve-3d;
    transition: transform 1s ease;
  }

  .card.flipped .card-front {
    transform: rotateY(180deg);
  }

  .card-image {
    position: absolute;
    width: 50%;
    height: 100%;
    object-fit: contain;
    pointer-events: none;
    top: 0;
    left: 0;
  }
  

  .card-content {
    position: absolute;
    bottom: var(--spacing-6);
    right: var(--spacing-6);
    display: flex;
    flex-direction: column;
    gap: var(--spacing-2);
    align-items: flex-end;
    z-index: 3;
  }

  .card-label {
    font-family: var(--font-secondary);
    font-weight: 700;
    font-size: 32px;
    color: black;
    margin: 0;
    white-space: nowrap;
  }

  .card-title {
    font-family: var(--font-secondary);
    font-weight: 700;
    font-size: var(--unit-64);
    color: black;
    margin: 0;
    line-height: 1;
    white-space: nowrap;
  }
</style>
