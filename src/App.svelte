<script>
	export let name;
	let agree = true;
	let text = "";
	let select = '1';
	let sex = 'male';
</script>

<main>
	<h1>{name}</h1>
	<input type="text" bind:value={name} />
	<hr />
	<input type="checkbox" bind:checked={agree} />
	{agree}
	<hr />
	<textarea bind:value={text}></textarea>
	<div style="white-space: pre-wrap">{text}</div>
	<hr />
	<select bind:value={select}> 
		<option value="0">Option 0</option>
		<option value="1">Option 1</option>
		<option value="2">Option 2</option>
	</select>
	<hr />
	<input type="radio" value="female" bind:group={sex}/>
	Female
	<input type="radio" value="male" bind:group={sex}/>
	Male
	<br />
	Sex: {sex}


</main>

<style> 
	main {
		text-align: left;
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