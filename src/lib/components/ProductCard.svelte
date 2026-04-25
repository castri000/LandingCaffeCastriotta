<script lang="ts">
  const { title = '', subtitle = '', description = '', imageUrl = '' } = $props<{
    title?: string;
    subtitle?: string;
    description?: string;
    imageUrl?: string;
  }>();
</script>

<button class="card">
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
    overflow: hidden;
    background: transparent;
    padding: 0;
    transition: transform 0.3s ease;
  }

  .card:hover {
    transform: translateY(-4px);
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
  }

  .card-description {
    width: 100%;
    text-align: left;
    transform: scaleY(-1) rotateY(180deg);
  }

  .card-description p {
    font-family: var(--font-secondary);
    font-weight: 400;
    font-size: 24px;
    color: var(--color-content-primary);
    line-height: 1.5;
    margin: 0;
  }

  .card-front {
    position: absolute;
    inset: 0;
    background: var(--brand-600);
    border-radius: var(--radius-xl);
    display: flex;
    align-items: flex-end;
    justify-content: flex-start;
    padding: var(--spacing-10);
    box-sizing: border-box;
    z-index: 2;
    transition: transform 0.3s ease;
  }

  .card:hover .card-front {
    transform: rotateY(180deg) scaleX(-1);
  }

  .card-image {
    position: absolute;
    top: -40px;
    right: 20px;
    width: 300px;
    height: auto;
    object-fit: contain;
    pointer-events: none;
  }

  .card-content {
    position: relative;
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
