<script>

	export let name;
	export let points;
	let showControls = false;

	const addPoint = () => points += 1;
	const removePoint = () => points -= 1;
	const toggleControls = () => (showControls = ! showControls);
</script>

<style>
	h1 {
		color: purple;
	}
	h3 {margin-bottom: 10px; }
</style>

<div class="container">
	<div class="card">
		<h1>
			{name}!
				<button class="btn" on:click={toggleControls}>
					{#if showControls}x{:else}={/if}
				</button>
		</h1>
		<h3>{points}</h3>
		{#if showControls}
			<button class="btn" on:click={addPoint}>+1</button>
			<button class="btn btn-dark" on:click={removePoint}>-1</button>
			<input type="number" bind:value={points}>
		{/if}

	</div>
</div>

