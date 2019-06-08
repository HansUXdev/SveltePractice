<script>
	let points = 100;
	let showControls = false;

	const toggleControls = () => (showControls = ! showControls);
</script>

<div class="pos-f-t">
  <nav class="navbar navbar-dark bg-dark">
    <button class="navbar-toggler" type="button" on:click={toggleControls} aria-controls="navbarToggleExternalContent" aria-expanded="false" aria-label="Toggle navigation">
      {#if showControls}
        <i class="fa fa-times"></i>
      {:else} 
        <span class="navbar-toggler-icon"></span>
      {/if}
    </button>
  </nav>
{#if showControls}
    <div class=" navbar-collapse bg-dark p-4">
      <ul class="navbar-nav mr-auto mt-2 mt-lg-0">
        <li class="nav-item active">
          <a class="nav-link" href="#">Home <span class="sr-only">(current)</span></a>
        </li>
        <li class="nav-item">
          <a class="nav-link" href="#">Link</a>
        </li>
      </ul>
    </div>
{:else}

{/if}
</div>


<style>
.nav-link{
  color: white;
}
</style>