<script>
	let points = 100;
	let showControls = false;

	const toggleControls = () => (showControls = ! showControls);
</script>

<div class="navbar bg-primary">
  <h1>Nav</h1>
  				<button class="btn" on:click={toggleControls}>
					{#if showControls}x{:else}={/if}
				</button>
</div>