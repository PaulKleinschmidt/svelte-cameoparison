<script>
	import Welcome from './screens/Welcome.svelte'
	export let state = 'welcome';

	const start = (e) => {
		console.log(e);
	};
</script>

<main>
	{#if state === 'welcome'}
		<Welcome on:select={start}/>
	{:else if state === 'playing'}
		<p>Playing screen goes here</p>
	{/if}
</main>

<style>
	main {
		text-align: center;
		padding: 1em;
		max-width: 800px;
		margin: 0 auto;
		height: 100%;
		display: flex;
		flex-direction: column;
		justify-content: center;
	}
</style>
