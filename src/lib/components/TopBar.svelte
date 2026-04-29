<script lang="ts">
  let activeLink = $state<'selezione' | 'about' | null>(null);

  function handleClick(link: 'selezione' | 'about') {
    activeLink = activeLink === link ? null : link;
  }
</script>

<div class="topbar">
  <div class="logo">CF</div>
  <nav class="nav-links">
    <button 
      class="nav-link" 
      class:active={activeLink === 'selezione'}
      onclick={() => handleClick('selezione')}
    >
      SELEZIONE
    </button>
    <button 
      class="nav-link" 
      class:active={activeLink === 'about'}
      onclick={() => handleClick('about')}
    >
      ABOUT
    </button>
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
    font-size: var(--unit-24);
    color: var(--color-content-primary);
    white-space: nowrap;
    padding: var(--spacing-7) var(--spacing-10);
  }

  .nav-links {
    display: flex;
    gap: var(--spacing-0);
    align-items: center;
  }

  .nav-link {
    font-family: var(--font-primary);
    font-weight: 700;
    font-size: var(--unit-24);
    color: var(--color-link-default);
    text-decoration: none;
    padding: var(--spacing-2) var(--spacing-6);
    right: var(--spacing-7);
    transition: all 0.3s ease;
    background: transparent;
    border: none;
    cursor: pointer;
    position: relative;
    border-radius: var(--radius-xl);
  }

  .nav-link:hover {
    color: var(--color-link-hover);
  }

  .nav-link.active {
    background: var(--brand-600);
    color: var(--color-link-default);
    border-radius: var(--radius-xl);
    padding: var(--spacing-2) var(--spacing-6);
    animation: slideIn 0.5s ease;
  }

  @keyframes slideIn {
    from {
      opacity: 0.7;
    }
    to {
      opacity: 1;
    }
  }


  /* RESPONSIVE TABLET */  
  @media (max-width: 744px){

  /* La topbar crea lo spazio laterale */
  .topbar {
    padding: var(--spacing-6) var(--spacing-6);
  }

  /* Il logo NON aggiunge spazio extra */
  .logo {
    font-size: var(--unit-20);
    padding: var(--spacing-0);
  }

  /* I link NON devono aggiungere spazio a destra */
  .nav-link {
    font-size: var(--unit-18);

    padding: var(--spacing-1) var(--spacing-2);
  }

  .nav-link.active {
    padding: var(--spacing-1) var(--spacing-2);
  }

  .nav-links {
    gap: var(--spacing-6);
  }
  }


  /* RESPONSIVE MOBILE */
  @media (max-width: 402px) {
    .topbar {
      padding: var(--spacing-5) var(--spacing-5);
    }

    .logo {
      font-size: var(--unit-18);
      padding: var(--spacing-0);
    }

    .nav-link {
      font-size: var(--unit-16);
      padding: var(--spacing-1) var(--spacing-2);
    }

    .nav-link.active {
      padding: var(--spacing-1) var(--spacing-2);
    }

    .nav-links {
      gap: var(--spacing-2);
    }
  }

</style>
