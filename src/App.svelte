<script>
	export let name;

	let counter = 0;
	$: counterClass = counter % 2 === 0 ? 'red' : 'blue';

	$: upperName = name.toUpperCase();
	$: lowerName = name.toLowerCase();

	$: {
		console.log("Name", name);
		console.log("Conunter", counter);
	}

	$: if (counter === 10){
		name = 'Counter is equal 10';
	}
	
	function changeName(){
		name = "New name";
	}
</script>

<main>
	<h1>Hello {name}!</h1>
	<h2>{upperName}</h2>
	<h2>{lowerName}</h2>
	<button on:click={changeName}>Change name</button>
	<h1 class={counterClass}>Counter {counter}</h1>
	<button on:click={() => counter++}>Add 1 to counter</button>
</main>

<style> 
	.blue {
		color: blue;
	}
	.red {
		color: red;
	}
	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}

	h1 {		
		text-transform: uppercase;
		font-size: 4em;
		font-weight: 100;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>