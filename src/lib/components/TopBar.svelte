<script lang="ts">
  const { device = 'Desktop' } = $props<{
  device?: 'Desktop' | 'Mobile';
}>();

</script>

<div class="topbar">
  <div class="logo">CF</div>
  <nav class="nav-links">
    <a href="#selezione" class="nav-link">SELEZIONE</a>
    <a href="#about" class="nav-link">ABOUT</a>
  </nav>
</div>

<style>
  .topbar {
    display: flex;
    align-items: center;
    justify-content: space-between;
    padding: var(--spacing/6) var(--spacing/10);
    width: 100%;
    box-sizing: border-box;
  }

  .logo {
    font-family: var(--font-primary);
    font-weight: 700;
    font-size: 24px;
    color: var(--color-content-primary);
    white-space: nowrap;
    padding: var(--spacing-7) var(--spacing-7);
  }

  .nav-links {
    display: flex;
    gap: var(--spacing-7);
    align-items: center;
  }

  .nav-link {
    font-family: var(--font-primary);
    font-weight: 700;
    font-size: 24px;
    color: var(--color-link-default);
    text-decoration: none;
    padding: var(--spacing-7) var(--spacing-7);
    transition: opacity 0.2s ease;
  }

  .nav-link:hover {
    color: var(--color-link-hover);
  }
</style>
