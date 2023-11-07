<script lang="ts">
	let start: boolean = false;
	let time: number = 120;
	let interval: number;
	let end: boolean = false;

	$: if (time === 0) start = false;
	$: if (time === 0) end = true;

	const startTimer = () => {
		if (start) return;
		start = true;
		interval = setInterval(() => {
			time--;
			if (time === 0) clearInterval(interval);
		}, 1000);
	};

	let scroll: number = 0;

	const scrollTonNextSlide = () => {
		if (start) window.scrollTo({ top: scroll, behavior: 'smooth' });
		scroll += window.innerHeight;
	};
</script>

<!-- svelte-ignore a11y-no-static-element-interactions -->
<!-- svelte-ignore a11y-click-events-have-key-events -->
<div id="control" on:click={scrollTonNextSlide}>
	<button on:click={startTimer}>
		{#if start}
			{time}s
		{:else}
			Start
		{/if}
	</button>
</div>

{#if end}
	<div id="end" />
{/if}

<style>
	#control {
		position: fixed;
		padding: 10px;
		right: 0;
	}

	button {
		width: 200px;
		height: 100px;
		display: flex;
		align-items: center;
		justify-content: center;
		color: wheat;
		background-color: black;
		border-radius: 20px;
		font-size: 40px;
		cursor: pointer;
	}

	#end {
		position: absolute;
		width: 100vw;
		height: 100vh;
		background-color: red;
		animation: fade 2s infinite;
	}

	@keyframes fade {
		0% {
			opacity: 1;
		}
		50% {
			opacity: 0;
		}
		100% {
			opacity: 1;
		}
	}
</style>
