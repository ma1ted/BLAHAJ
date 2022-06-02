<script>
	import { fly } from "svelte/transition";
	import { onMount } from "svelte";

	export let showContent = () => {};

	const lineCount = 3;
	const interLineDelay = 100;
	const lineDuration = 500;

	let show = false;
	onMount(() => {
		show = true;
		setTimeout(() => {
			show = false;
			setTimeout(() => {
				showContent();
			}, lineCount * interLineDelay + lineDuration);
		}, lineCount * interLineDelay + lineDuration);
	});
</script>

{#if show}
	<section class="container">
		{#each Array(lineCount) as _, index}
			<div
				in:fly={{
					x: -window.innerWidth,
					duration: lineDuration,
					delay: index * interLineDelay
				}}
				out:fly={{
					x: window.innerWidth,
					duration: lineDuration,
					delay: index * interLineDelay
				}}
			/>
		{/each}
	</section>
{/if}

<style>
	.container {
		height: 100%;
		display: flex;
		flex-direction: column;
		justify-content: center;
	}
	.container > div {
		height: 20%;
	}
	.container > div:nth-of-type(1),
	.container > div:nth-of-type(3) {
		background-color: #f5a9b8;
	}
	.container > div:nth-of-type(2) {
		background-color: white;
	}
</style>
