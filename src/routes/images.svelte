<!-- <script>
    import { onMount } from "svelte";
    
    const imageCount = 14;
    let container;
    let imageIndex = 0;

    function loadImage(index) {
        if (index > imageCount) return;

        const panel = document.createElement("div");
        panel.className = "panel";
        
        const img = document.createElement("img");
        img.src = `/blahaj/blahaj-${index}.jpg`;
        img.alt = "BLÅHAJ";
        img.className = "blahaj";
        img.style.width = "100%";

        panel.appendChild(img);
        container.appendChild(panel)
        
        imageIndex++;
        img.onload = () => loadImage(imageIndex);
    }
    
    onMount(() => loadImage(imageIndex));
</script>

<section class="container" bind:this={container}>

</section> -->

<section class="container">
	{#each Array(15) as _, index}
		<div class="panel">
			<img class="blahaj" src="/blahaj/blahaj-{index}.jpg" loading="lazy" alt="BLÅHAJ"/>
		</div>
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
