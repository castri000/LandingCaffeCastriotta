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


  @media (max-width: 744px) {

  .quote-section {
    padding: var(--spacing-6) var(--spacing-8);
    min-height: auto;

    /* RISOLVE IL PROBLEMA DEI BORDI */
    max-width: calc(100% - 48px); /* 24px per lato */
    margin: 0 auto;
  }

  .quote-text {
    font-size: var(--unit-24);
    line-height: 1.4;

    /* RISOLVE IL PROBLEMA DEL TESTO TROPPO STRETTO */
    max-width: 640px;
    margin: 0 auto;

    /* SE VUOI GIUSTIFICATO COME L’ALTRA SEZIONE */
    text-align: center;
  }
}


</style>
