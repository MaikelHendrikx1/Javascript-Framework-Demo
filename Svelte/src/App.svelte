<script>
	let catFacts = [];

	function GenerateCatFact(){
		fetch('https://catfact.ninja/fact')
    	.then((response) => response.json())
    	.then((responseJSON) => {
			catFacts.push(responseJSON.fact);
			catFacts = catFacts;
    	});
	}
	
</script>

<main>
	{#each catFacts as catFact}
		<h2>{catFact}</h2>
		<hr>
	{/each}

	<button on:click={GenerateCatFact}>Generate a cat fact!</button>
</main>

<style>
	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
		max-width: none;
	}
</style>