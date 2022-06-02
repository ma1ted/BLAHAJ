<script>
	import { fade } from "svelte/transition";

	import Trans from "./trans.svelte";
	import Title from "./title.svelte";
	import Images from "./images.svelte";
	import Footer from "./footer.svelte";

	let intro = true;
	let content = false;

	const showContent = () => (content = true);
</script>

{#if intro}
	<Trans {showContent} />
{/if}
{#if content}
	<section in:fade>
		<Title />
		<Images />
		<Footer />
	</section>
{/if}

<style>
	@font-face {
		font-family: "IKEA Noto";
		src: url("/fonts/noto-ikea-400.woff2") format("woff2");
		font-weight: 400;
	}
	@font-face {
		font-family: "IKEA Noto";
		src: url("/fonts/noto-ikea-700.woff2") format("woff2");
		font-weight: 700;
	}
	:global(*) {
		font-family: "IKEA Noto", sans-serif;
		color: white;
		margin: 0;
	}
	:global(html, body) {
		margin: 0;
		width: 100%;
		height: 100%;
		background-color: #5bcefa;
	}
</style>
