<script>
	let value = 'hello';
	$: error = !isValid(value);
	function isValid(val){
		return val.length > 5 && val.length < 10;
	}
</script>

<main>
	<h1>Application {value}</h1>
	<input type="text" bind:value={value} class:red={error} class:green={!error}>

	{#if value.length < 5 }
	<p>Длинна меньше 5 смволов</p>
	{:else if value.length > 10}
	<p>Длинна больше 10 символов</p>
	{:else}
	<p>Длина между 5 и 10 символами</p>
	{/if}
</main>

<style> 
	input {
		outline: none;
	}
	.red {
		border-color: red;
	}
	.green {
		border-color: green;
	}
</style>