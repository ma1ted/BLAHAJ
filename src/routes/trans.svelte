<script>
	import { fly, fade } from "svelte/transition";
	import { onMount } from "svelte";

	const lineCount = 3;
	const interLineDelay = 100;
	const lineDuration = 500;
    const animationDuration = lineCount * interLineDelay + lineDuration;

	let showFlag = false;
    let showCover = true;
	onMount(() => {
		showFlag = true;
        showCover = false;
		setTimeout(() => {
			showFlag = false;
		}, animationDuration);
	});
</script>

{#if showCover}
    <div id="cover"></div>
{/if}

{#if showFlag}
	<section class="container" out:fade={{duration: animationDuration}}>
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
    #cover {
        position: fixed;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
        background-color: var(--blue);
    }
	.container {
        position: fixed;
        top: 0;
        left: 0;
		height: 100%;
        width: 100%;
		display: flex;
		flex-direction: column;
		justify-content: center;
        background-color: var(--blue);
        z-index: 3;
	}
	.container > div {
		height: 20%;
	}
	.container > div:nth-of-type(1),
	.container > div:nth-of-type(3) {
		background-color: var(--pink);
	}
	.container > div:nth-of-type(2) {
		background-color: white;
	}
</style>
