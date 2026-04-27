<script lang="ts">
  let isFlipped = $state(false);

  const { title = '', subtitle = '', description = '', imageUrl = '',side = 'left' } = $props<{
    title?: string;
    subtitle?: string;
    description?: string;
    imageUrl?: string;
    side?: 'left' | 'right';
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

  <div class="card-front" data-side={side}>
    {#if imageUrl}
      <img src={imageUrl} alt={title} class="card-image" data-side={side} />
    {/if}

    <div class="card-content" data-side={side}  >
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
  }

  .card-back,
  .card-front {
  position: absolute;
  inset: 0;
  border-radius: var(--radius-xl);
  backface-visibility: hidden;
  transition: transform 0.8s ease;
  }

  .card-back {  
    background: var(--brand-800);  
    display: flex;
    align-items: center;
    justify-content: center;
    padding: var(--spacing-10);
    box-sizing: border-box;
    transform: rotateY(180deg);
  }

  .card.flipped .card-back {
    transform: rotateY(0deg);
  }

  .card-front {
    background: var(--brand-600);
  }

  .card.flipped .card-front {
    transform: rotateY(180deg);
  }



  .card-description p {
    font-family: var(--font-primary);
    font-weight: 400;
    font-size: var(--unit-24);
    color: var(--color-content-primary);
    line-height: 1.5;
    margin: 0;
    text-align: left;
  }

  .card-image {
    position: absolute;
    top: 50%;
    width: auto;
    height: 75%;
    object-fit: contain;
    pointer-events: none;
    backface-visibility: hidden;
    z-index: 1;
  }

  /* POSIZIONE IMMAGINE SINISTRA / DESTRA */
  .card-image[data-side="left"] {
  left: 0.5%;
  transform: translateY(-50%) rotate(20deg) scale(1.25);
  }

  .card-image[data-side="right"] {
  right: 0.5%;
  transform: translateY(-50%) rotate(-20deg) scale(1.25);
  }
  

  .card-content {
    position: absolute;
    bottom: var(--spacing-6);
    display: flex;
    flex-direction: column;
    gap: var(--spacing-2);
    z-index: 3;
  }

  .card-content[data-side="left"] {
  right: var(--spacing-6);
  text-align: right;
  }

  .card-content[data-side="right"] {
  left: var(--spacing-6);
  text-align: left;
  }

  .card-label {
    font-family: var(--font-secondary);
    font-weight: 700;
    font-size: var(--unit-48);
    color: var(--color-background-primary);
    margin: 0;
  }

  .card-title {
    font-family: var(--font-secondary);
    font-weight: 700;
    font-size: var(--unit-64);
    color: var(--color-background-primary);
    margin: 0;
    line-height: 1;
  }
</style>
