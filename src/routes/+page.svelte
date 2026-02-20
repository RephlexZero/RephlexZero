<script lang="ts">
	import { base } from '$app/paths';
</script>

<svelte:head>
	<title>RephlexZero — Developer Portfolio</title>
	<meta name="description" content="Personal portfolio showcasing projects, skills, and experience." />
</svelte:head>

<section class="hero">
	<div class="hero-content">
		<p class="greeting">Hi, I'm</p>
		<h1>RephlexZero</h1>
		<p class="tagline">
			I build things for the web — crafting <span class="highlight">fast</span>,
			<span class="highlight">accessible</span>, and <span class="highlight">beautiful</span> digital experiences.
		</p>
		<div class="cta-group">
			<a href="{base}/projects" class="btn btn-primary">View Projects</a>
			<a href="{base}/contact" class="btn btn-outline">Get In Touch</a>
		</div>
	</div>
	<div class="hero-glow" aria-hidden="true"></div>
</section>

<style>
	.hero {
		min-height: 100dvh;
		display: flex;
		align-items: center;
		justify-content: center;
		padding: var(--space-xl) var(--space-lg);
		position: relative;
		overflow: hidden;
	}

	.hero-content {
		max-width: var(--max-width);
		position: relative;
		z-index: 1;
	}

	.greeting {
		font-family: var(--font-mono);
		color: var(--color-accent);
		font-size: 1rem;
		margin-bottom: var(--space-sm);
	}

	h1 {
		font-size: clamp(2.5rem, 8vw, 5rem);
		font-weight: 700;
		letter-spacing: -0.03em;
		line-height: 1.1;
		margin-bottom: var(--space-md);
	}

	.tagline {
		font-size: clamp(1rem, 2.5vw, 1.25rem);
		color: var(--color-text-muted);
		max-width: 600px;
		line-height: 1.7;
		margin-bottom: var(--space-xl);
	}

	.highlight {
		color: var(--color-text);
		font-weight: 600;
	}

	.cta-group {
		display: flex;
		gap: var(--space-md);
		flex-wrap: wrap;
	}

	.btn {
		display: inline-flex;
		align-items: center;
		padding: 0.75rem 1.75rem;
		border-radius: var(--radius-md);
		font-weight: 600;
		font-size: 0.9rem;
		transition: all var(--transition);
	}

	.btn-primary {
		background: var(--color-accent);
		color: white;
	}

	.btn-primary:hover {
		background: var(--color-accent-hover);
		box-shadow: 0 0 30px var(--color-accent-glow);
	}

	.btn-outline {
		border: 1px solid var(--color-border);
		color: var(--color-text);
	}

	.btn-outline:hover {
		border-color: var(--color-accent);
		color: var(--color-accent);
	}

	.hero-glow {
		position: absolute;
		width: 600px;
		height: 600px;
		background: radial-gradient(circle, var(--color-accent-glow) 0%, transparent 70%);
		top: 50%;
		left: 60%;
		transform: translate(-50%, -50%);
		pointer-events: none;
	}

	@media (max-width: 640px) {
		.hero {
			padding-top: 6rem;
		}
	}
</style>
