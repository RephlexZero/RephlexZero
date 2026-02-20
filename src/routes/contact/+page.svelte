<script lang="ts">
	let name = $state('');
	let email = $state('');
	let message = $state('');
	let submitted = $state(false);

	function handleSubmit(e: SubmitEvent) {
		const form = e.target as HTMLFormElement;
		const data = new FormData(form);

		fetch(form.action, {
			method: 'POST',
			body: data,
			headers: { 'Accept': 'application/json' }
		}).then(res => {
			if (res.ok) {
				submitted = true;
				name = '';
				email = '';
				message = '';
			}
		});

		e.preventDefault();
	}
</script>

<svelte:head>
	<title>Contact — Jake Stewart</title>
</svelte:head>

<section class="contact">
	<h1 class="gradient-text">Get In Touch</h1>
	<p class="subtitle">
		Want to chat about a project, an idea, or just say hi? Go for it.
	</p>

	{#if submitted}
		<div class="success-msg">
			<span class="success-icon">&#10003;</span>
			<p>Message sent! I'll get back to you soon.</p>
		</div>
	{:else}
		<form
			action="https://formspree.io/f/jake.reflex@gmail.com"
			method="POST"
			class="form"
			onsubmit={handleSubmit}
		>
			<label>
				<span>Name</span>
				<input type="text" name="name" bind:value={name} required autocomplete="name" />
			</label>
			<label>
				<span>Email</span>
				<input type="email" name="email" bind:value={email} required autocomplete="email" />
			</label>
			<label>
				<span>Message</span>
				<textarea name="message" bind:value={message} rows="5" required></textarea>
			</label>
			<button type="submit" class="btn btn-primary">Send Message</button>
		</form>
	{/if}

	<div class="alt-contact">
		<p>Or find me here</p>
		<div class="social-links">
			<a href="https://github.com/RephlexZero" target="_blank" rel="noopener noreferrer" class="social-chip social-gh">
				GitHub
			</a>
			<a href="https://www.linkedin.com/in/jake-stewart-360444272/" target="_blank" rel="noopener noreferrer" class="social-chip social-li">
				LinkedIn
			</a>
			<a href="mailto:jake.reflex@gmail.com" class="social-chip social-email">
				Email
			</a>
		</div>
	</div>
</section>

<style>
	.contact {
		max-width: 600px;
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
		font-size: 1.05rem;
	}

	.success-msg {
		display: flex;
		align-items: center;
		gap: var(--space-md);
		padding: var(--space-lg);
		background: var(--color-emerald-glow);
		border: 1px solid rgba(52, 211, 153, 0.3);
		border-radius: var(--radius-lg);
	}

	.success-icon {
		font-size: 1.5rem;
		color: var(--color-emerald);
	}

	.success-msg p {
		color: var(--color-emerald);
		font-weight: 500;
	}

	.form {
		display: flex;
		flex-direction: column;
		gap: var(--space-lg);
	}

	label {
		display: flex;
		flex-direction: column;
		gap: var(--space-xs);
	}

	label span {
		font-size: 0.85rem;
		font-weight: 500;
		color: var(--color-text-muted);
	}

	input,
	textarea {
		font: inherit;
		font-size: 0.95rem;
		background: var(--color-surface);
		border: 1px solid var(--color-border);
		border-radius: var(--radius-md);
		padding: 0.75rem 1rem;
		color: var(--color-text);
		transition: border-color var(--transition), box-shadow var(--transition);
		resize: vertical;
	}

	input:focus,
	textarea:focus {
		outline: none;
		border-color: var(--color-accent);
		box-shadow: 0 0 0 3px var(--color-accent-glow);
	}

	.btn-primary {
		display: inline-flex;
		align-items: center;
		justify-content: center;
		padding: 0.8rem 2rem;
		border-radius: var(--radius-full);
		font-weight: 600;
		font-size: 0.9rem;
		background: var(--gradient-primary);
		color: white;
		transition: all var(--transition);
		align-self: flex-start;
		box-shadow: 0 0 20px var(--color-accent-glow);
	}

	.btn-primary:hover {
		transform: translateY(-2px);
		box-shadow: 0 0 40px var(--color-accent-glow);
	}

	.alt-contact {
		margin-top: var(--space-xl);
		padding-top: var(--space-xl);
		border-top: 1px solid var(--color-border);
	}

	.alt-contact p {
		color: var(--color-text-muted);
		font-size: 0.9rem;
		margin-bottom: var(--space-md);
	}

	.social-links {
		display: flex;
		gap: var(--space-md);
		flex-wrap: wrap;
	}

	.social-chip {
		font-family: var(--font-mono);
		font-size: 0.85rem;
		font-weight: 600;
		padding: 0.5rem 1.2rem;
		border-radius: var(--radius-full);
		transition: all var(--transition);
		border: 1px solid transparent;
	}

	.social-gh {
		color: var(--color-text);
		background: var(--color-surface-2);
		border-color: var(--color-border);
	}
	.social-gh:hover {
		border-color: var(--color-text);
		box-shadow: 0 0 16px rgba(255, 255, 255, 0.05);
	}

	.social-li {
		color: #0a66c2;
		background: rgba(10, 102, 194, 0.1);
		border-color: rgba(10, 102, 194, 0.2);
	}
	.social-li:hover {
		background: rgba(10, 102, 194, 0.2);
		box-shadow: 0 0 16px rgba(10, 102, 194, 0.1);
	}

	.social-email {
		color: var(--color-rose);
		background: var(--color-rose-glow);
		border-color: rgba(251, 113, 133, 0.2);
	}
	.social-email:hover {
		background: rgba(251, 113, 133, 0.2);
		box-shadow: 0 0 16px var(--color-rose-glow);
	}
</style>
