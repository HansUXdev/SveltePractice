<script>
  import { createEventDispatcher } from "svelte";
  const dispatch = createEventDispatcher();

	export let name;
	export let points;
	let showControls = false;

	const addPoint = () => points += 1;
	const removePoint = () => points -= 1;
	const toggleControls = () => (showControls = ! showControls);
	const onDelete = () => dispatch("removePlayer", name);
</script>

<style>
	h1 {
		color: purple;
	}
	h3 {margin-bottom: 10px; }
	.card{margin: 1em auto}
</style>


			<div class="card" style="width: 18rem;">
				<div class="card-header">
					<ul class="nav nav-tabs card-header-tabs">
						<li class="nav-item">
							<a class="nav-link active">Score</a>
						</li>
						<li class="nav-item">
							<button class="btn" on:click={toggleControls}>Edit</button>
						</li>
						<li class="nav-item">
							<button class="btn" on:click={onDelete}>Remove</button>
						</li>
					</ul>
				</div>
				<div class="card-header">
					{name}
				</div>
				<div class="card-body">
				{#if showControls}
					<div class="card-body">
						<button class="btn btn-secondary" on:click={addPoint}>
						+1
						</button>
						<button class="btn btn-dark" on:click={removePoint}>
						-1
						</button>
						<input type="number" bind:value={points}>
					</div>
					{:else}
					<h5 class="card-title">{points}</h5>
					<!--
					<p class="card-text">...</p>
					-->
				{/if}
				</div>
			</div>	

