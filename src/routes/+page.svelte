<script lang="ts">
	import Timer from '$lib/components/Timer.svelte';
	import Image from '$lib/components/Image.svelte';
</script>

<Timer />

<div id="intro">
	<h1>Internet of animals</h1>
	<h3>Envisioning non-human perspectives</h3>
	<p>By Felix Willen</p>
</div>

<Image src="https://source.unsplash.com/random/800x600" />
<Image src="https://source.unsplash.com/random/800x600" />
<Image src="https://source.unsplash.com/random/800x600" />
<Image src="https://source.unsplash.com/random/800x600" />

<style>
	:global(body) {
		margin: 0;
		padding: 0;
		font-family: sans-serif;
		background-color: black;
	}
	#intro {
		width: 100vw;
		height: 100vh;
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
		color: wheat;
	}

	p {
		color: wheat;
	}
</style>
