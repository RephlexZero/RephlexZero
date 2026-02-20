<svelte:head>
	<title>About — RephlexZero</title>
</svelte:head>

<section class="about">
	<h1>About Me</h1>
	<div class="content">
		<div class="bio">
			<p>
				I'm a developer passionate about building modern web applications. I enjoy working with
				cutting-edge technologies and turning ideas into polished, performant products.
			</p>
			<p>
				When I'm not coding, you'll find me exploring new technologies, contributing to open source,
				or learning something new.
			</p>
		</div>
		<div class="skills">
			<h2>Tech I Work With</h2>
			<ul class="skill-grid">
				{#each ['TypeScript', 'Svelte', 'React', 'Node.js', 'Python', 'Docker', 'Git', 'SQL'] as skill}
					<li>{skill}</li>
				{/each}
			</ul>
		</div>
	</div>
</section>

<style>
	.about {
		max-width: var(--max-width);
		margin: 0 auto;
		padding: 8rem var(--space-lg) var(--space-xl);
	}

	h1 {
		font-size: clamp(2rem, 5vw, 3rem);
		font-weight: 700;
		letter-spacing: -0.03em;
		margin-bottom: var(--space-xl);
	}

	.content {
		display: grid;
		grid-template-columns: 1fr 1fr;
		gap: var(--space-xl);
	}

	.bio p {
		color: var(--color-text-muted);
		margin-bottom: var(--space-md);
		line-height: 1.8;
	}

	h2 {
		font-size: 1.25rem;
		margin-bottom: var(--space-md);
	}

	.skill-grid {
		display: grid;
		grid-template-columns: 1fr 1fr;
		gap: var(--space-sm);
		list-style: none;
	}

	.skill-grid li {
		font-family: var(--font-mono);
		font-size: 0.875rem;
		color: var(--color-text-muted);
		padding: var(--space-sm) var(--space-md);
		border: 1px solid var(--color-border);
		border-radius: var(--radius-sm);
		transition: all var(--transition);
	}

	.skill-grid li:hover {
		border-color: var(--color-accent);
		color: var(--color-accent);
		background: var(--color-accent-glow);
	}

	@media (max-width: 768px) {
		.content {
			grid-template-columns: 1fr;
		}
	}
</style>
