<script>
	import { enhance } from '$app/forms';
    let {data} = $props();
</script>

<h1>Create a new Categorie</h1>

<div class="container">
	<form method="POST" action="?/createCategorie" use:enhance>

		<label class="label2" for="name">name</label>
		<textarea placeholder="Name" name="name"></textarea>

    
 
		<button type="submit">Create Categorie</button>
	</form>
</div>

<style>
	
    h1 {
		font-size: 32px;
		color: #f57ce1;
		text-align: center;
		margin-bottom: 24px;
		font-weight: 500;
	}



	label {
		font-size: 16px;
		font-weight: 600;
		margin-bottom: 8px;
		color: #686868;
	}

	button {
		background-color: #6d0077;
		color: #fff;
		padding: 12px 20px;
		font-size: 16px;
		border: none;
		border-radius: 4px;
		cursor: pointer;
		transition: background-color 0.3s ease;
		font-weight: 600;
	}


</style>
