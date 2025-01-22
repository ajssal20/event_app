<script>
	import {flip} from 'svelte/animate';
	let { data } = $props();
	let filteredEvents = $state(data.events);
	let selectedCategory = $state('all');

	function filterEvents(){
		if (selectedCategory ==='all'){
			filteredEvents = data.events;
		} else{
			filteredEvents= data.events.filter( e=> e.category_id === selectedCategory.id);
		}
	}
</script>





<div>
	{#if data.user}
	<p> Welcome back , {data.user.username}</p>
		<form action="/logout?/logout" method="post">
		<button type="submit">Logout</button>
		
		</form>

		<form action="/logout?/deleteAccount" method="post">

			<button type="submit">Delete Accout</button>
			
		</form>
		

	{:else}
		<p>
			You are not logged in. 
			
		</p>
		

		<a href="/login">Login</a>
		or 
		<a href="/register">Register</a>
	{/if}

</div>







<h1>My Event App</h1>
<p>Here are the current events.</p>



<select name="" id="" bind:value={selectedCategory} onchange={filterEvents}>
	<option value="all">ALL</option>
	{#each data.categories as category}
	<option value="{category}"> {category.name}</option>
{/each}
</select>
<div class="Bukur">
{#each filteredEvents as event (event.id)}
		<article animate:flip>
	<p>{event.id} - {event.title} - { new Date(event.start_date).toDateString()}</p>
	
</article>
{/each}
</div>
<style>
	h1{
		display: flex;
		align-items: center;
		justify-content: center;
		font:  sans-serif;
		font-size: 100px;
		color: rgb(66, 0, 66);

	}
	p{

		color: rgb(70, 0, 70);
		font:  sans-serif;
		font-size: 20px;
	}
	.Bukur{
		margin: 20px;
		background-color: rgb(66, 142, 243);
	
	}

</style>