<svelte:head>
	<title>About — Jake Stewart</title>
</svelte:head>

<section class="about">
	<h1 class="gradient-text">About Me</h1>
	<div class="content">
		<div class="bio">
			<p>
				I'm Jake — an Electrical & Electronic Engineering student who likes building things that
				live close to the metal. From PCB design and firmware to Linux systems and networking,
				I enjoy working across the full stack of hardware and embedded software.
			</p>
			<p>
				My projects tend to start with a problem I want to solve — whether that's bonding cellular
				connections for live video, designing custom input devices, or making a rover drive itself.
				I reach for Rust and C first, Python when I need to move fast, and Git and Docker everywhere.
			</p>
			<p>
				Outside of engineering, you'll find me tinkering with keyboards, sim racing, or diving
				into whatever rabbit hole caught my attention this week.
			</p>
		</div>
		<div class="skills">
			<h2>What I Use</h2>
			<ul class="skill-grid">
				{#each [
					{ name: 'Rust', color: 'rose' },
					{ name: 'C / C++', color: 'accent' },
					{ name: 'Python', color: 'amber' },
					{ name: 'Linux', color: 'emerald' },
					{ name: 'KiCad', color: 'cyan' },
					{ name: 'Docker', color: 'cyan' },
					{ name: 'Git', color: 'rose' },
					{ name: 'GStreamer', color: 'amber' },
					{ name: 'Embedded Systems', color: 'emerald' },
					{ name: 'PCB Design', color: 'accent' }
				] as skill}
					<li class="skill-{skill.color}">{skill.name}</li>
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
		animation: fade-up 0.6s ease both;
	}

	h1 {
		font-size: clamp(2rem, 5vw, 3.5rem);
		font-weight: 700;
		letter-spacing: -0.03em;
		margin-bottom: var(--space-xl);
	}

	.content {
		display: grid;
		grid-template-columns: 1.2fr 1fr;
		gap: var(--space-xl);
	}

	.bio p {
		color: var(--color-text-muted);
		margin-bottom: var(--space-md);
		line-height: 1.8;
		font-size: 1.05rem;
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
		font-size: 0.85rem;
		padding: var(--space-sm) var(--space-md);
		border-radius: var(--radius-md);
		transition: all var(--transition);
		border: 1px solid transparent;
	}

	.skill-rose { color: var(--color-rose); background: var(--color-rose-glow); border-color: rgba(251, 113, 133, 0.2); }
	.skill-accent { color: var(--color-accent-hover); background: var(--color-accent-glow); border-color: rgba(99, 102, 241, 0.2); }
	.skill-amber { color: var(--color-amber); background: var(--color-amber-glow); border-color: rgba(251, 191, 36, 0.2); }
	.skill-emerald { color: var(--color-emerald); background: var(--color-emerald-glow); border-color: rgba(52, 211, 153, 0.2); }
	.skill-cyan { color: var(--color-cyan); background: var(--color-cyan-glow); border-color: rgba(34, 211, 238, 0.2); }

	.skill-grid li:hover {
		transform: translateY(-2px);
		box-shadow: 0 4px 20px rgba(0, 0, 0, 0.3);
	}

	@media (max-width: 768px) {
		.content {
			grid-template-columns: 1fr;
		}
	}
</style>
