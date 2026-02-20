<footer>
	<div class="footer-inner">
		<p class="copyright">&copy; {new Date().getFullYear()} RephlexZero. All rights reserved.</p>
		<div class="links">
			<a href="https://github.com" target="_blank" rel="noopener noreferrer">GitHub</a>
			<a href="https://linkedin.com" target="_blank" rel="noopener noreferrer">LinkedIn</a>
		</div>
	</div>
</footer>

<style>
	footer {
		border-top: 1px solid var(--color-border);
		padding: var(--space-lg);
		margin-top: var(--space-2xl);
	}

	.footer-inner {
		max-width: var(--max-width);
		margin: 0 auto;
		display: flex;
		align-items: center;
		justify-content: space-between;
		flex-wrap: wrap;
		gap: var(--space-md);
	}

	.copyright {
		font-size: 0.875rem;
		color: var(--color-text-muted);
	}

	.links {
		display: flex;
		gap: var(--space-lg);
	}

	.links a {
		font-size: 0.875rem;
		color: var(--color-text-muted);
		transition: color var(--transition);
	}

	.links a:hover {
		color: var(--color-accent);
	}
</style>
