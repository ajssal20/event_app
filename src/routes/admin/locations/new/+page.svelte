<script>
	import { enhance } from '$app/forms';
</script>

<h1>Create a new event</h1>

<form method="POST" action="?/createLocation" use:enhance>
	<label for="name">Name</label>
	<input type="text" placeholder="Name" name="name" />

	<label for="street">Street</label>
	<textarea placeholder="Street" name="street"></textarea>

	<button type="submit">Create locations</button>
</form>
