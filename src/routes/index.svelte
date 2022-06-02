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

<svelte:head>
    <!-- Primary Meta Tags -->
    <title>BLÅHAJ</title>
    <meta name="title" content="BLÅHAJ">
    <meta name="description" content="Alla älskar den här lilla blåhajen. Det ger de bästa kramarna. Det spelar ingen roll om du gråter in i det. Det är det bästa.">

    <!-- Open Graph / Facebook -->
    <meta property="og:type" content="website">
    <meta property="og:url" content="https://blahaj.malted.dev/">
    <meta property="og:title" content="BLÅHAJ">
    <meta property="og:description" content="Alla älskar den här lilla blåhajen. Det ger de bästa kramarna. Det spelar ingen roll om du gråter in i det. Det är det bästa.">
    <meta property="og:image" content="https://blahaj.malted.dev/blahaj/blahaj-0.png">

    <!-- Twitter -->
    <meta property="twitter:card" content="summary_large_image">
    <meta property="twitter:url" content="https://blahaj.malted.dev/">
    <meta property="twitter:title" content="BLÅHAJ">
    <meta property="twitter:description" content="Alla älskar den här lilla blåhajen. Det ger de bästa kramarna. Det spelar ingen roll om du gråter in i det. Det är det bästa.">
    <meta property="twitter:image" content="https://blahaj.malted.dev/blahaj/blahaj-0.png">

</svelte:head>

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
