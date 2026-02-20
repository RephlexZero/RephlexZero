<script lang="ts">
	const projects = [
		{
			title: 'Project One',
			description: 'A brief description of this project and what it does. Replace with your real projects.',
			tags: ['SvelteKit', 'TypeScript', 'Vercel'],
			link: '#',
			repo: '#'
		},
		{
			title: 'Project Two',
			description: 'Another project description. Showcase your best work here.',
			tags: ['React', 'Node.js', 'PostgreSQL'],
			link: '#',
			repo: '#'
		},
		{
			title: 'Project Three',
			description: 'One more project to round things out. Add as many as you like.',
			tags: ['Python', 'Docker', 'AWS'],
			link: '#',
			repo: '#'
		}
	];
</script>

<svelte:head>
	<title>Projects — RephlexZero</title>
</svelte:head>

<section class="projects">
	<h1>Projects</h1>
	<p class="subtitle">A selection of things I've built.</p>

	<div class="grid">
		{#each projects as project}
			<article class="card">
				<h2>{project.title}</h2>
				<p>{project.description}</p>
				<ul class="tags">
					{#each project.tags as tag}
						<li>{tag}</li>
					{/each}
				</ul>
				<div class="card-links">
					{#if project.link !== '#'}
						<a href={project.link} target="_blank" rel="noopener noreferrer">Live ↗</a>
					{/if}
					{#if project.repo !== '#'}
						<a href={project.repo} target="_blank" rel="noopener noreferrer">Code ↗</a>
					{/if}
				</div>
			</article>
		{/each}
	</div>
</section>

<style>
	.projects {
		max-width: var(--max-width);
		margin: 0 auto;
		padding: 8rem var(--space-lg) var(--space-xl);
	}

	h1 {
		font-size: clamp(2rem, 5vw, 3rem);
		font-weight: 700;
		letter-spacing: -0.03em;
		margin-bottom: var(--space-sm);
	}

	.subtitle {
		color: var(--color-text-muted);
		margin-bottom: var(--space-xl);
	}

	.grid {
		display: grid;
		grid-template-columns: repeat(auto-fill, minmax(320px, 1fr));
		gap: var(--space-lg);
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
		border-color: var(--color-accent);
		transform: translateY(-2px);
		box-shadow: 0 8px 30px rgba(0, 0, 0, 0.3);
	}

	.card h2 {
		font-size: 1.25rem;
		margin-bottom: var(--space-sm);
	}

	.card p {
		color: var(--color-text-muted);
		font-size: 0.9rem;
		line-height: 1.7;
		flex: 1;
		margin-bottom: var(--space-md);
	}

	.tags {
		display: flex;
		flex-wrap: wrap;
		gap: var(--space-xs);
		list-style: none;
		margin-bottom: var(--space-md);
	}

	.tags li {
		font-family: var(--font-mono);
		font-size: 0.75rem;
		color: var(--color-accent);
		background: var(--color-accent-glow);
		padding: 0.2rem 0.6rem;
		border-radius: var(--radius-full);
	}

	.card-links {
		display: flex;
		gap: var(--space-md);
	}

	.card-links a {
		font-size: 0.85rem;
		font-weight: 500;
		color: var(--color-text-muted);
		transition: color var(--transition);
	}

	.card-links a:hover {
		color: var(--color-accent);
	}
</style>
