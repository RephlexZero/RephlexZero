<script lang="ts">
  import { page } from "$app/state";
  import { base } from "$app/paths";

  const links = [
    { href: `${base}/`, label: "Home" },
    { href: `${base}/about`, label: "About" },
    { href: `${base}/projects`, label: "Projects" },
    { href: `${base}/contact`, label: "Contact" },
  ] as const;

  let scrolled = $state(false);

  function handleScroll() {
    scrolled = window.scrollY > 20;
  }
</script>

<svelte:window onscroll={handleScroll} />

<nav class:scrolled>
  <div class="nav-inner">
    <a href="{base}/" class="logo">
      <span class="logo-accent">&lt;</span>RZ<span class="logo-accent">
        /&gt;</span
      >
    </a>
    <ul>
      {#each links as { href, label }}
        <li>
          <a {href} class:active={page.url.pathname === href}>
            {label}
          </a>
        </li>
      {/each}
    </ul>
  </div>
</nav>

<style>
  nav {
    position: fixed;
    top: 0;
    left: 0;
    right: 0;
    z-index: 100;
    padding: var(--space-md) var(--space-lg);
    transition:
      background var(--transition),
      backdrop-filter var(--transition);
  }

  nav.scrolled {
    background: rgba(10, 10, 10, 0.8);
    backdrop-filter: blur(12px);
    border-bottom: 1px solid var(--color-border);
  }

  .nav-inner {
    max-width: var(--max-width);
    margin: 0 auto;
    display: flex;
    align-items: center;
    justify-content: space-between;
  }

  .logo {
    font-family: var(--font-mono);
    font-size: 1.25rem;
    font-weight: 700;
    letter-spacing: -0.02em;
  }

  .logo-accent {
    background: var(--gradient-primary);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
  }

  ul {
    display: flex;
    list-style: none;
    gap: var(--space-lg);
  }

  ul a {
    font-size: 0.875rem;
    font-weight: 500;
    color: var(--color-text-muted);
    transition: color var(--transition);
    position: relative;
  }

  ul a:hover,
  ul a.active {
    color: var(--color-text);
  }

  ul a.active::after {
    content: "";
    position: absolute;
    bottom: -4px;
    left: 0;
    right: 0;
    height: 2px;
    background: var(--gradient-primary);
    border-radius: var(--radius-full);
  }

  @media (max-width: 640px) {
    ul {
      gap: var(--space-md);
    }
  }
</style>
