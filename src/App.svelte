<script>
	import Modal from './Modal.svelte';

	let people = [
		{name: "Jack", beltColour: "black", age: 23, id: 1},
		{name: "Luke", beltColour: "orange", age: 23, id: 2},
		{name: "Conal", beltColour: "purple", age: 26, id: 3}
	];

	const handleClick = (id) => {
		people = people.filter((person) => id != person.id);
	}
</script>

<Modal message="Hey, I am a prop value" isPromo={true} />

<main>
	{#each people as person (person.id)}
		<div>
			<h4>{person.name}</h4>
			{#if person.beltColour === "black"}
				<p><strong>Master ninja</strong></p>
			{/if}
			<p>{person.age} years old</p>
			<p>{person.beltColour} belt</p>
			<button on:click={() => handleClick(person.id)}>delete</button>
		</div>
	{/each}
</main>

<style>
	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>