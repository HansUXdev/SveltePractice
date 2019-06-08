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
	const removePlayer = (e) => {
		players =  players.filter(player => player.name !== e.detail);
	}

	function typewriter(node, { speed = 50 }) {
		const valid = (
			node.childNodes.length === 1 &&
			node.childNodes[0].nodeType === 3
		);

		if (!valid) return {};

		const text = node.textContent;
		const duration = text.length * speed;

		return {
			duration,
			tick: (t, u) => {
				const i = ~~(text.length * t);
				node.textContent = text.slice(0, i);
			}
		};
	}

</script>


<Navbar />

<div class="container">


	<p in:typewriter="{{ speed: 120 }}">
		A very basic typing effect with vanillia js...
	</p>




	<div class="container">
		<AddPlayer on:addplayer={addPlayer} />
	{#if players.length === 0 }
		<p>No Players</p>
		{:else}
			<div class="row">
			{#each players as player}
				<div class="col">
					<Player 
						name={player.name} 
						points={player.points}
						on:removePlayer={removePlayer}
					/>
				</div>
			{/each}
			</div>
	{/if}
	</div>
</div>


<style>
	/* h1 {
		color: purple;
	}
	h3 {margin-bottom: 10px; } */
</style>
