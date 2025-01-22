<script>
	import { enhance } from '$app/forms';
	import { slide } from 'svelte/transition';
	let { data } = $props();
</script>

<div class="container">
	<h1>Events</h1>

	<a href="/admin/events/new">Create a new event</a>
</div>

{#each data.events as event (event.id)}
	<div class="box" transition:slide>
		<p>{event.id} - {event.title} - {event.locationName} - {event.start_date}</p>

		<form action="?/deleteEvent" method="POST" use:enhance>
			<input type="hidden" name="id" value={event.id} />
			<button type="submit">Delete</button>
		</form>
	</div>
{/each}



<style>
	.box {
		border: 3px solid #880000;
		padding: 1rem;
		margin: 1rem 0;
	}

	.container {
		display: flex;
		align-items: center;
		justify-content: center;
		flex-direction: column;
		background-color: rgb(248, 175, 220);
	}

	.box {
		padding: 10px;
		margin: 20px;
		box-shadow: 1px 3px 2px 1px rgb(94, 0, 0);
		
	}


</style>
