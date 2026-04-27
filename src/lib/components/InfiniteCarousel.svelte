<script lang="ts">
  import { onMount } from 'svelte';

  const brands = ['MOTTA', 'BORBONE', 'LAVAZZA', 'ILLY', 'BIALETTI', 'NESCAFÈ', 'VERGNANO'];
  const repeatedBrands = Array(2).fill(brands).flat();

  let carouselContent: HTMLElement;
  let scrollPosition = 0;

  onMount(() => {
    const scrollWidth = carouselContent.scrollWidth / 2; // metà della larghezza totale

    const animate = () => {
      scrollPosition += 1; // velocità di scroll
      
      if (scrollPosition >= scrollWidth) {
        scrollPosition = 0; // reset invisibile perché il contenuto si ripete
      }
      
      carouselContent.style.transform = `translateX(-${scrollPosition}px)`;
      requestAnimationFrame(animate);
    };

    animate();
  });
</script>

<div class="carousel">
  <div class="carousel-content" bind:this={carouselContent}>
    {#each repeatedBrands as brand, index}
      <span key={index} class="brand-item">{brand}</span>
      <span class="separator">-</span>
    {/each}
  </div>
</div>

<style>
  .carousel {
    width: 100%;
    overflow: hidden;
    padding: var(--spacing-6) var(--spacing-10);
    box-sizing: border-box;
  }

  .carousel-content {
    display: flex;
    gap: var(--spacing-6);
    align-items: center;
    font-family: var(--font-secondary);
    font-weight: 700;
    font-size: 24px;
    color: white;
    white-space: nowrap;
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
      transform: translateX(-100%);
    }
  }
</style>
