<script>
	import Person from './Person.svelte'
	let value = "";
	let people = [
		{id: 1,name: 'Максим'},
		{id: 2,name: 'Елена'},
		{id: 3,name: 'Татьяна'}
	]
	function addPerson(){
 		// people = people.concat([{
		// 	id: Date.now(),
		// 	name: value
		// }]);
		people = [
			...people,
			{
				id: Date.now(),
				name: value
			}
		]
		value = ""; 
	}
	function removeFirst(){
		people = people.slice(1);
	}
</script>

<main>
<input type="text" bind:value />
<button on:click={addPerson}>Add person</button>
<button on:click={removeFirst}>Remove first</button>
<hr />
{#each people as { name, id }, i (id)}
	<Person {name} index={i}/>
{:else}
	<p>No people!</p>
{/each}
</main>

<style> 
</style>