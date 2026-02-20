<script lang="ts">
	import { base } from '$app/paths';
</script>

<svelte:head>
	<title>Jake Stewart — Embedded Engineer</title>
	<meta name="description" content="Embedded systems engineer specialising in Rust, C, Linux, and hardware design." />
</svelte:head>

<section class="hero">
	<div class="hero-bg" aria-hidden="true">
		<div class="orb orb-1"></div>
		<div class="orb orb-2"></div>
		<div class="orb orb-3"></div>
		<div class="grid-overlay"></div>
	</div>

	<div class="hero-content">
		<p class="greeting">Hey, I'm</p>
		<h1 class="gradient-text">Jake Stewart</h1>
		<p class="tagline">
			Embedded engineer building things at the intersection of
			<span class="chip chip-rust">Rust</span>
			<span class="chip chip-c">C</span>
			<span class="chip chip-hw">Hardware</span>
			and
			<span class="chip chip-linux">Linux</span>
		</p>
		<p class="sub">EEE student. I design circuits, write firmware, and occasionally make software that talks to the real world.</p>
		<div class="cta-group">
			<a href="{base}/projects" class="btn btn-primary">See My Work</a>
			<a href="{base}/contact" class="btn btn-outline">Say Hello</a>
		</div>
	</div>
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

	.hero-bg {
		position: absolute;
		inset: 0;
		z-index: 0;
	}

	.grid-overlay {
		position: absolute;
		inset: 0;
		background-image:
			linear-gradient(rgba(99, 102, 241, 0.03) 1px, transparent 1px),
			linear-gradient(90deg, rgba(99, 102, 241, 0.03) 1px, transparent 1px);
		background-size: 60px 60px;
		mask-image: radial-gradient(ellipse 70% 60% at 50% 40%, black 20%, transparent 100%);
	}

	.orb {
		position: absolute;
		border-radius: 50%;
		filter: blur(100px);
		animation: float 12s ease-in-out infinite;
	}

	.orb-1 {
		width: 500px; height: 500px;
		background: radial-gradient(circle, rgba(99, 102, 241, 0.3), transparent 70%);
		top: 10%; left: 15%;
	}

	.orb-2 {
		width: 400px; height: 400px;
		background: radial-gradient(circle, rgba(34, 211, 238, 0.2), transparent 70%);
		top: 40%; right: 10%;
		animation-delay: -4s;
	}

	.orb-3 {
		width: 350px; height: 350px;
		background: radial-gradient(circle, rgba(251, 113, 133, 0.15), transparent 70%);
		bottom: 10%; left: 40%;
		animation-delay: -8s;
	}

	@keyframes float {
		0%, 100% { transform: translate(0, 0) scale(1); }
		33% { transform: translate(30px, -20px) scale(1.05); }
		66% { transform: translate(-20px, 15px) scale(0.95); }
	}

	.hero-content {
		max-width: var(--max-width);
		position: relative;
		z-index: 1;
		animation: fade-up 0.8s ease both;
	}

	.greeting {
		font-family: var(--font-mono);
		color: var(--color-cyan);
		font-size: 1rem;
		margin-bottom: var(--space-sm);
	}

	h1 {
		font-size: clamp(3rem, 10vw, 6rem);
		font-weight: 700;
		letter-spacing: -0.04em;
		line-height: 1.05;
		margin-bottom: var(--space-lg);
	}

	.tagline {
		font-size: clamp(1rem, 2.5vw, 1.2rem);
		color: var(--color-text-muted);
		max-width: 640px;
		line-height: 2;
		margin-bottom: var(--space-sm);
	}

	.sub {
		font-size: 1rem;
		color: var(--color-text-muted);
		max-width: 540px;
		line-height: 1.7;
		margin-bottom: var(--space-xl);
	}

	.chip {
		display: inline-block;
		font-family: var(--font-mono);
		font-size: 0.8rem;
		font-weight: 600;
		padding: 0.15rem 0.6rem;
		border-radius: var(--radius-full);
		vertical-align: middle;
	}

	.chip-rust {
		background: rgba(251, 113, 133, 0.15);
		color: var(--color-rose);
		border: 1px solid rgba(251, 113, 133, 0.3);
	}
	.chip-c {
		background: rgba(99, 102, 241, 0.15);
		color: var(--color-accent-hover);
		border: 1px solid rgba(99, 102, 241, 0.3);
	}
	.chip-hw {
		background: rgba(251, 191, 36, 0.15);
		color: var(--color-amber);
		border: 1px solid rgba(251, 191, 36, 0.3);
	}
	.chip-linux {
		background: rgba(52, 211, 153, 0.15);
		color: var(--color-emerald);
		border: 1px solid rgba(52, 211, 153, 0.3);
	}

	.cta-group {
		display: flex;
		gap: var(--space-md);
		flex-wrap: wrap;
	}

	.btn {
		display: inline-flex;
		align-items: center;
		padding: 0.8rem 2rem;
		border-radius: var(--radius-full);
		font-weight: 600;
		font-size: 0.9rem;
		transition: all var(--transition);
	}

	.btn-primary {
		background: var(--gradient-primary);
		color: white;
		box-shadow: 0 0 24px var(--color-accent-glow);
	}

	.btn-primary:hover {
		box-shadow: 0 0 40px var(--color-accent-glow), 0 0 80px rgba(34, 211, 238, 0.1);
		transform: translateY(-2px);
	}

	.btn-outline {
		border: 1px solid var(--color-border);
		color: var(--color-text);
	}

	.btn-outline:hover {
		border-color: var(--color-cyan);
		color: var(--color-cyan);
		box-shadow: 0 0 20px var(--color-cyan-glow);
	}

	@media (max-width: 640px) {
		.hero {
			padding-top: 6rem;
		}
	}
</style>
