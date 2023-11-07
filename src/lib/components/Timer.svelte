<script lang="ts">
	let start: boolean = false;
	let time: number = 120;
	let interval: number;

	const startTimer = () => {
		if (start) return;
		start = true;
		interval = setInterval(() => {
			time--;
			if (time === 0) clearInterval(interval);
		}, 1000);
	};

	const scrollTonNextSlide = () => {
		if (start) window.scrollBy(0, window.innerHeight);
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
</style>
