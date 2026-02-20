<script lang="ts">
  const featured = [
    {
      title: "Strata",
      description:
        "Open-source bonded cellular video transport — a free alternative to $15k LiveU hardware. Bonds 2–6 network links (cellular, WiFi, Ethernet) into a single resilient live video stream. Ships as a GStreamer plugin and standalone CLI, built for ARM64 field hardware.",
      tags: ["Rust", "GStreamer", "Networking", "Linux"],
      repo: "https://github.com/RephlexZero/strata",
      color: "rose",
      stars: 1,
    },
    {
      title: "MoonPad",
      description:
        "A custom Hall Effect keypad designed from scratch in KiCad — PCB layout, schematic, and case design. Built for high-performance gaming input with analog key sensing.",
      tags: ["KiCad", "PCB Design", "Hardware", "Hall Effect"],
      repo: "https://github.com/RephlexZero/MoonPad",
      color: "cyan",
      stars: 3,
    },
  ];

  const other = [
    {
      title: "VIPS Rover",
      description:
        "Autonomously navigating rover using the Racelogic VIPS positioning system.",
      tags: ["Python", "Robotics"],
      repo: "https://github.com/RephlexZero/vips_rover",
      color: "amber",
    },
    {
      title: "Cascade Circuit Solver",
      description: "Tool for analysing and solving cascaded circuit networks.",
      tags: ["Python", "EEE"],
      repo: "https://github.com/RephlexZero/Cascade-Circuit-Solver",
      color: "emerald",
    },
    {
      title: "minipad-firmware",
      description:
        "Hall Effect keypad firmware with rapid trigger support, designed for low-latency input.",
      tags: ["C++", "Embedded", "Firmware"],
      repo: "https://github.com/RephlexZero/minipad-firmware",
      color: "accent",
    },
    {
      title: "QMK Firmware",
      description:
        "Contributions to the open-source keyboard firmware for custom keyboard builds.",
      tags: ["C", "Firmware", "USB"],
      repo: "https://github.com/RephlexZero/qmk_firmware",
      color: "rose",
    },
  ];
</script>

<svelte:head>
  <title>Projects — Jake Stewart</title>
</svelte:head>

<section class="projects">
  <h1 class="gradient-text">Projects</h1>
  <p class="subtitle">Things I've designed, built, and shipped.</p>

  <div class="featured-grid">
    {#each featured as project}
      <a
        href={project.repo}
        target="_blank"
        rel="noopener noreferrer"
        class="featured-card card-{project.color}"
      >
        <div class="card-glow" aria-hidden="true"></div>
        <div class="card-inner">
          <div class="card-header">
            <h2>{project.title}</h2>
            {#if project.stars}
              <span class="stars">&#9733; {project.stars}</span>
            {/if}
          </div>
          <p>{project.description}</p>
          <ul class="tags">
            {#each project.tags as tag}
              <li>{tag}</li>
            {/each}
          </ul>
          <span class="link-hint">View on GitHub &#8599;</span>
        </div>
      </a>
    {/each}
  </div>

  <h2 class="section-label">Other Projects</h2>
  <div class="grid">
    {#each other as project}
      <a
        href={project.repo}
        target="_blank"
        rel="noopener noreferrer"
        class="card card-{project.color}"
      >
        <h3>{project.title}</h3>
        <p>{project.description}</p>
        <ul class="tags">
          {#each project.tags as tag}
            <li>{tag}</li>
          {/each}
        </ul>
      </a>
    {/each}
  </div>
</section>

<style>
  .projects {
    max-width: var(--max-width);
    margin: 0 auto;
    padding: 8rem var(--space-lg) var(--space-xl);
    animation: fade-up 0.6s ease both;
  }

  h1 {
    font-size: clamp(2rem, 5vw, 3.5rem);
    font-weight: 700;
    letter-spacing: -0.03em;
    margin-bottom: var(--space-sm);
  }

  .subtitle {
    color: var(--color-text-muted);
    margin-bottom: var(--space-xl);
    font-size: 1.1rem;
  }

  /* Featured cards — big, glowing, prominent */
  .featured-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(420px, 1fr));
    gap: var(--space-lg);
    margin-bottom: var(--space-2xl);
  }

  .featured-card {
    position: relative;
    border-radius: var(--radius-xl);
    overflow: hidden;
    transition: all 300ms cubic-bezier(0.4, 0, 0.2, 1);
    display: block;
  }

  .featured-card .card-glow {
    position: absolute;
    inset: 0;
    opacity: 0;
    transition: opacity 400ms ease;
    border-radius: var(--radius-xl);
  }

  .featured-card:hover .card-glow {
    opacity: 1;
  }

  .card-rose .card-glow {
    background: radial-gradient(
      ellipse at 30% 20%,
      rgba(251, 113, 133, 0.1),
      transparent 70%
    );
  }
  .card-cyan .card-glow {
    background: radial-gradient(
      ellipse at 70% 80%,
      rgba(34, 211, 238, 0.1),
      transparent 70%
    );
  }

  .featured-card .card-inner {
    position: relative;
    z-index: 1;
    padding: var(--space-xl);
    background: var(--color-surface);
    border: 1px solid var(--color-border);
    border-radius: var(--radius-xl);
    height: 100%;
    display: flex;
    flex-direction: column;
    transition: border-color 300ms ease;
  }

  .card-rose:hover .card-inner {
    border-color: rgba(251, 113, 133, 0.4);
  }
  .card-cyan:hover .card-inner {
    border-color: rgba(34, 211, 238, 0.4);
  }

  .featured-card:hover {
    transform: translateY(-4px);
  }

  .card-header {
    display: flex;
    align-items: center;
    justify-content: space-between;
    margin-bottom: var(--space-md);
  }

  .featured-card h2 {
    font-size: 1.5rem;
    font-weight: 700;
  }

  .card-rose h2 {
    color: var(--color-rose);
  }
  .card-cyan h2 {
    color: var(--color-cyan);
  }

  .stars {
    font-family: var(--font-mono);
    font-size: 0.85rem;
    color: var(--color-amber);
  }

  .featured-card p {
    color: var(--color-text-muted);
    font-size: 0.95rem;
    line-height: 1.7;
    flex: 1;
    margin-bottom: var(--space-md);
  }

  .link-hint {
    font-size: 0.85rem;
    font-weight: 600;
    color: var(--color-text-muted);
    margin-top: var(--space-sm);
    transition: color var(--transition);
  }

  .card-rose:hover .link-hint {
    color: var(--color-rose);
  }
  .card-cyan:hover .link-hint {
    color: var(--color-cyan);
  }

  /* Tags */
  .tags {
    display: flex;
    flex-wrap: wrap;
    gap: var(--space-xs);
    list-style: none;
    margin-bottom: var(--space-md);
  }

  .tags li {
    font-family: var(--font-mono);
    font-size: 0.7rem;
    padding: 0.2rem 0.6rem;
    border-radius: var(--radius-full);
    background: var(--color-surface-2);
    color: var(--color-text-muted);
    border: 1px solid var(--color-border);
  }

  /* Section label */
  .section-label {
    font-size: 1.1rem;
    color: var(--color-text-muted);
    margin-bottom: var(--space-lg);
    font-weight: 600;
  }

  /* Smaller cards */
  .grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
    gap: var(--space-md);
  }

  .card {
    background: var(--color-surface);
    border: 1px solid var(--color-border);
    border-radius: var(--radius-lg);
    padding: var(--space-lg);
    transition: all var(--transition);
    display: flex;
    flex-direction: column;
  }

  .card:hover {
    transform: translateY(-2px);
    box-shadow: 0 8px 30px rgba(0, 0, 0, 0.3);
  }

  .card-amber:hover {
    border-color: rgba(251, 191, 36, 0.4);
  }
  .card-emerald:hover {
    border-color: rgba(52, 211, 153, 0.4);
  }
  .card-accent:hover {
    border-color: rgba(99, 102, 241, 0.4);
  }
  .card-rose:not(.featured-card):hover {
    border-color: rgba(251, 113, 133, 0.4);
  }

  .card h3 {
    font-size: 1.1rem;
    margin-bottom: var(--space-sm);
  }

  .card-amber h3 {
    color: var(--color-amber);
  }
  .card-emerald h3 {
    color: var(--color-emerald);
  }
  .card-accent h3 {
    color: var(--color-accent-hover);
  }
  .card-rose:not(.featured-card) h3 {
    color: var(--color-rose);
  }

  .card p {
    color: var(--color-text-muted);
    font-size: 0.9rem;
    line-height: 1.7;
    flex: 1;
    margin-bottom: var(--space-md);
  }

  @media (max-width: 768px) {
    .featured-grid {
      grid-template-columns: 1fr;
    }
  }
</style>
