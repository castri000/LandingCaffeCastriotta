<script lang="ts">
  const brands = ['MOTTA', 'BORBONE', 'LAVAZZA', 'ILLY', 'BIALETTI', 'NESCAFÈ', 'VERGNANO'];
  const repeatedBrands = [...brands, ...brands];
</script>

<div class="carousel">
  <div class="carousel-content">
    {#each repeatedBrands as brand, index}
      <span key={index} class="brand-item">{brand}</span>
      {#if index < repeatedBrands.length - 1}
        <span class="separator">-</span>
      {/if}
    {/each}
  </div>
</div>

<style>
  .carousel {
    width: 100%;
    overflow: hidden;
    padding: var(--spacing/6) var(--spacing/10);
    box-sizing: border-box;
  }

  .carousel-content {
    display: flex;
    gap: var(--spacing/6);
    align-items: center;
    font-family: var(--font-secondary);
    font-weight: 700;
    font-size: 24px;
    color: white;
    white-space: nowrap;
    animation: scroll 30s linear infinite;
  }

  .brand-item {
    flex-shrink: 0;
  }

  .separator {
    flex-shrink: 0;
    color: white;
  }

  @keyframes scroll {
    0% {
      transform: translateX(0);
    }
    100% {
      transform: translateX(-50%);
    }
  }
</style>
