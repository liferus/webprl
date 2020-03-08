<script>
	import Person from './Person.svelte'
	const people = [
		{id: 1,name: 'Максим', age: 24, job: 'Frontend'},
		{id: 2,name: 'Елена', age: 17, job: 'Студент'}
	]
	let name = 'Igor'
	let age = 20
	let jobTitle = 'Backend'
</script>

<main>
	<h1>Application</h1>
	<Person name={people[0].name} age={people[0].age} job={people[0].job} />
	<Person {...people[1]} />
	<Person {name} {age} job={jobTitle} />
</main>

<style> 
</style>