<section class="container">
	{#each Array(15) as _, index}
		<a class="panel" href="/blarge/blahaj-{index}.png">
			<img
				class="blahaj"
				src="/blahaj/blahaj-{index}.jpg"
				loading="lazy"
				alt="BLÅHAJ"
			/>
		</a>
	{/each}
</section>

<style>
	.container {
		display: grid;
		grid-template-columns: 1fr 1fr;
		gap: 3rem;
		margin: 3rem;
	}
	@media (max-width: 600px) {
		.container {
			grid-template-columns: 1fr;
			gap: 2rem;
			margin: 2rem;
		}
	}
	@media (min-width: 1800px) {
		.container {
			grid-template-columns: 1fr 1fr 1fr;
			gap: 5rem;
			margin: 5rem;
		}
	}

	.panel {
		text-align: center;
		height: 100%;
		display: flex;
		flex-direction: column;
		align-items: center;
	}
	.blahaj {
		width: 100%;
	}
</style>
