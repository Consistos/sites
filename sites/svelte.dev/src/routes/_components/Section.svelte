<section>
	<div class="inner"><slot /></div>
</section>

<style>
	section {
		padding-block: 2rem;
		background: var(--background, white);
	}

	.inner {
		max-inline-size: 12rem;
		padding-inline: var(--side-nav);
		margin-inline: auto;
		margin-block: 0;
	}
</style>
