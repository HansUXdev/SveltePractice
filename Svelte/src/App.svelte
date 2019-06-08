<script>
	import Navbar from './Navbar.svelte';
	import Player from './Player.svelte';
	import AddPlayer from './AddPlayer.svelte';
	let players = [
		{
			name: "Brett",
			points: 80
		},
		{
			name: "Brittany",
			points: 45
		},
		{
			name: "Xander",
			points: 99
		}
	]
	const addPlayer = (e) => {
		const newPlayer = e.detail;
		players = [...players, newPlayer];
	}
</script>


<Navbar />

<div class="container">
	<AddPlayer on:addPlayer={addPlayer}/>

	{#if players.length === 0 }
		<p>No Players</p>
		{:else}
			{#each players as player}
				<Player 
					name={player.name} 
					points={player.points}
				/>
			{/each}
	{/if}
</div>


<style>
	/* h1 {
		color: purple;
	}
	h3 {margin-bottom: 10px; } */
</style>
