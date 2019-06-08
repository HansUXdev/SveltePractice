<script>
  import { createEventDispatcher } from "svelte";
  const dispatch = createEventDispatcher();

  let player = {
    name: "",
    points: 0
  };
  const onSubmit = e => {
    e.preventDefault();
    dispatch("addplayer", player);
    player = {
      name: "",
      points: 0
    };
  };
</script>

<form class="form-inline" on:submit={onSubmit}>
  <div class="form-group mb-2">
    <label for="name" class="sr-only">Email</label>
    <input type="text" class="form-control" placeholder="Player Name"  id="name"  bind:value={player.name} />
  </div>
  <div class="form-group mx-sm-3 mb-2">
    <label for="points" class="sr-only">Password</label>
    <input type="number" class="form-control" id="points" placeholder="Player Points" bind:value={player.points} />
  </div>
  <button type="submit" class="btn btn-primary mb-2">Add Player</button>
</form>