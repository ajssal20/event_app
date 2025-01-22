<script>
	let { children } = $props();
</script>

<nav class="container">
	<a href="/admin/events"> Events</a>
	<a href="/admin/locations">Location</a>
	<a href="/admin/categories">Categories</a>
</nav>

{@render children()}

<style>
	.container {
		display: flex;
		justify-content: center;
		align-items: center;
		height: 50px;
		width: 100%;
		background-color: rgb(240, 109, 185);
		text-decoration: none;
	}
	
	
		
	
	



</style>
