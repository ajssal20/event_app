<script>
	import { enhance } from '$app/forms';
	import { slide } from 'svelte/transition';
	let { data , form } = $props();
</script>

<div class="container">
	<h1>Categorie</h1>

	<a href="/admin/categories/new">Create a new categorie</a>
</div>

{#if  form && !form.successs}
<Warning message={form.message}/>
	
{/if}




{#each data.categories as categorie (categorie.id)}
	<div class="box" transition:slide>
		<p>{categorie.id} - {categorie.name}</p>

		<form action="?/deleteCategorie" method="POST" use:enhance>
			<input type="hidden" name="id" value={categorie.id} />
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
