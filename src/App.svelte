<script>
	export let name;
	function changeNameHandler(){
		name += "click ";
	}
	let pos = {
		x: 0,
		y: 0
	}
	let inputValue = "";
	function mouseMoveHandler(event){
		pos.x=event.x;
		pos.y=event.y;
	}
	function submitHandler(event){
		console.log("inputValue: ", inputValue);
	}
</script>

<main>
	<h1>Hello {name}!</h1>
	<button on:click={changeNameHandler}>Change name</button>
	<div class="playground" on:mousemove={mouseMoveHandler}>
	<h2>X: {pos.x}, Y:{pos.y}</h2>
	</div>
	<form on:submit|preventDefault|once ={submitHandler}>
		<input type="text" on:input={event => (inputValue = event.target.value)}/>
		<button type="submit">Submit form</button>
	</form>
</main>

<style> 
	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}

	h1 {
		color: #ff3e00;
		text-transform: uppercase;
		font-size: 4em;
		font-weight: 100;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
	.playground {
		width: 400px;
		height: 200px;
		padding: 1rem;
		margin-bottom: 1rem;
		border: 1px solid black;
	}
</style>