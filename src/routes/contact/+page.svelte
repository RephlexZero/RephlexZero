<script lang="ts">
	let name = $state('');
	let email = $state('');
	let message = $state('');
</script>

<svelte:head>
	<title>Contact — RephlexZero</title>
</svelte:head>

<section class="contact">
	<h1>Get In Touch</h1>
	<p class="subtitle">
		Have a question or want to work together? Drop me a message.
	</p>

	<form
		action="https://formspree.io/f/YOUR_FORM_ID"
		method="POST"
		class="form"
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

	<div class="alt-contact">
		<p>Or find me on</p>
		<div class="social-links">
			<a href="https://github.com" target="_blank" rel="noopener noreferrer">GitHub</a>
			<a href="https://linkedin.com" target="_blank" rel="noopener noreferrer">LinkedIn</a>
			<a href="mailto:you@example.com">Email</a>
		</div>
	</div>
</section>

<style>
	.contact {
		max-width: 600px;
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
		transition: border-color var(--transition);
		resize: vertical;
	}

	input:focus,
	textarea:focus {
		outline: none;
		border-color: var(--color-accent);
	}

	.btn-primary {
		display: inline-flex;
		align-items: center;
		justify-content: center;
		padding: 0.75rem 1.75rem;
		border-radius: var(--radius-md);
		font-weight: 600;
		font-size: 0.9rem;
		background: var(--color-accent);
		color: white;
		transition: all var(--transition);
		align-self: flex-start;
	}

	.btn-primary:hover {
		background: var(--color-accent-hover);
		box-shadow: 0 0 30px var(--color-accent-glow);
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
		gap: var(--space-lg);
	}

	.social-links a {
		font-weight: 500;
		color: var(--color-text-muted);
		transition: color var(--transition);
	}

	.social-links a:hover {
		color: var(--color-accent);
	}
</style>
