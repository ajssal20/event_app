<script>
	import { enhance } from '$app/forms';
	import { slide } from 'svelte/transition';
	let { data , form} = $props();
</script>

<h1>Locations</h1>

<a href="/admin/locations/new">Create a new location</a>

{#if  form && !form.successs}
<Warning message={form.message}/>
{/if}

{#each data.locations as locations (locations.id)}
	<div class="box" transition:slide>
		<p>{locations.id} - {locations.name}</p>

		<form action="?/deleteLocations" method="POST" use:enhance>
			<input type="hidden" name="id" value={locations.id} />
			<button type="submit">Delete</button>
		</form>
	</div>
{/each}

<style>

	h1{
		padding: 10px;
		margin: 20px;
		display: flex;
		align-items: center;
		justify-content: center;
		flex-direction: column;
		background-color: rgb(248, 175, 220);

	}

	a{
		text-decoration: none;
		display: flex;
		justify-content: center;
		align-items: center;
		color: black;
	}

</style>
