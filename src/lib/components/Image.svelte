<script lang="ts">
	export let src: string;
</script>

<img {src} alt="slide" />

<style>
	img {
		width: 100vw;
		height: 100vh;
		object-fit: cover;
	}
</style>
