<script lang="ts">
  const { heading = '', subheading = '', description = '' } = $props<{
    heading?: string;
    subheading?: string;
    description?: string;
  }>();
</script>

<section class="text-image-section">
  <div class="text-content">
    <h2 class="section-heading">{heading}</h2>
    <h3 class="section-subheading">{subheading}</h3>
    <p class="section-description">{description}</p>
  </div>
  <div class="image-content">
    <slot />
  </div>
</section>

<style>
  .text-image-section {
    display: flex;
    gap: var(--spacing-10);
    align-items: center;
    justify-content: center;
    padding: var(--spacing-7) var(--spacing-7);
    width: 100%;
    box-sizing: border-box;
  }

  .text-content {
    flex: 0 0 auto;
    width: 50%;
    display: flex;
    flex-direction: column;
    gap: var(--spacing-7);
    justify-content: center;
  }

  .section-heading {
    font-family: var(--font-primary);
    font-weight: 700;
    font-size: var(--unit-72);
    color: var(--color-content-primary);
    margin: 0;
    line-height: 1.2;
  }

  .section-subheading {
    font-family: var(--font-primary);
    font-weight: 500;
    font-size: var(--unit-48);
    color: var(--color-content-primary);
    margin: 0;
    line-height: 1.2;
  }

  .section-description {
    font-family: var(--font-primary);
    font-weight: 300;
    font-size: var(--unit-24);
    color: var(--color-content-primary);
    line-height: 1.4;
    text-align: justify;
    margin: 0;
    max-width: 704px;
  }

  .image-content {
    flex: 0 0 auto;
  }


  @media (max-width: 744px) {

  .text-image-section {
    flex-direction: column;
    padding: var(--spacing-7) var(--spacing-10);
    gap: var(--spacing-10);
    text-align: left;

    /* QUESTA È LA PARTE CHE RISOLVE IL PROBLEMA */
    max-width: calc(100% - 32px); /* 16px per lato */
    margin: 0 auto;
  }

  .text-content {
    width: 100%;
    max-width: 620px;
    margin: 0 auto;
    gap: var(--spacing-5);
  }

  .section-heading {
    font-size: var(--unit-48);
  }

  .section-subheading {
    font-size: var(--unit-40);
  }

  .section-description {
    font-size: var(--unit-20);
    max-width: 620px;
    margin: 0 auto;
    text-align: justify;
  }

  .image-content {
    display: none;
  }
}


</style>
