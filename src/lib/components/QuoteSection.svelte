<script lang="ts">
  const { quote = '' } = $props<{
    quote?: string;
  }>();
</script>

<div class="quote-section">
  <p class="quote-text">{quote}</p>
</div>

<style>
  .quote-section {
    display: flex;
    align-items: center;
    justify-content: center;
    padding: var(--spacing-10) var(--spacing-10);
    width: 100%;
    box-sizing: border-box;
    min-height: 328px;
  }

  .quote-text {
    font-family: var(--font-primary);
    font-weight: 700;
    font-size: var(--unit-48);
    color: var(--color-content-primary);
    text-align: center;
    line-height: 1.4;
    margin: 0;
    max-width: 1175px;
  }
</style>
