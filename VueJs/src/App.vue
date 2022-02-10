<script>
  export default{
    data(){
      return {
        catFacts: []
      }
    },
    methods: {
      GenerateCatFact(){
		    fetch('https://catfact.ninja/fact')
        .then((response) => response.json())
        .then((responseJSON) => {
        this.catFacts.push(responseJSON.fact);
      });
	    }
    }
  }
</script>


<template>
  <main >
    <div v-for="catFact in catFacts" :key="catFact">
      <h2>{{catFact}}</h2>
      <hr>
    </div>
    <button @click="GenerateCatFact();">Generate a cat fact!</button>
  </main>
</template>


<style>
	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
		max-width: none;
	}
</style>