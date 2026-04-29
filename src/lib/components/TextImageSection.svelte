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


  /* RESPONSIVE TABLET */
  @media (max-width: 744px) {

  .text-image-section {
    flex-direction: column;
    padding: var(--spacing-6) var(--spacing-6);
    gap: var(--spacing-6);
    text-align: left;

    /* QUESTA È LA PARTE CHE RISOLVE IL PROBLEMA */
    max-width: calc(100% - 48px); /* 16px per lato */
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


  /* RESPONSIVE MOBILE */
  @media (max-width: 402px) {

  .text-image-section {
    flex-direction: column;
    padding: var(--spacing-4) var(--spacing-5); /* molto più compatto */
    gap: var(--spacing-4); /* come nel Figma */
    max-width: calc(100% - 24px);
    margin: 0 auto;
    text-align: center;
  }

  .text-content {
    width: 100%;
    max-width: 320px;
    margin: 0 auto;
    gap: var(--spacing-3);
  }

  .section-heading {
    font-size: var(--unit-32);
  }

  .section-subheading {
    font-size: var(--unit-24);
  }

  .section-description {
    font-size: var(--unit-16);
    line-height: 1.4;
    text-align: justify;
  }

  .image-content {
    display: none; /* già fatto, ma lo confermo */
  }
}





</style>
