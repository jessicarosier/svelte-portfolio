<script>
	import Nav from './Nav.svelte';
	import Hero from './Hero.svelte';
</script>

<main>
	<Nav />

	<div class="container">
		<Hero />

	</div>



</main>

<style>




	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>