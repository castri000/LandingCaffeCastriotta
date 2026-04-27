<script lang="ts">
  import ProductCard from './ProductCard.svelte';

  interface CardData {
    title: string;
    subtitle: string;
    description: string;
    imageUrl: string;
  }

  const { cards = [] } = $props<{
    cards?: CardData[];
  }>();
</script>

<div class="cards-grid">
  {#each cards as card}
    <ProductCard
      title={card.title}
      subtitle={card.subtitle}
      description={card.description}
      imageUrl={card.imageUrl}
      side={card.side}
    />
  {/each}
</div>

<style>
  .cards-grid {
    display: flex;
    flex-wrap: wrap;
    gap: 23px;
    align-items: center;
    justify-content: center;
    padding: var(--spacing-7) var(--spacing-7);
    width: 100%;
    box-sizing: border-box;
  }
</style>
