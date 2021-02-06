<script>
	import { } from 'os'
	import { text } from 'svelte/internal'
	import Modal from './Modal.svelte'
	import AddPersonForm from './AddPersonForm.svelte'

	let showModal = false

	// Test data
	let people = [
		{ name: 'yoshi', beltColour: 'black', age: 25, id: 1},
		{ name: 'mario', beltColour: 'orange', age: 45, id: 2},
		{ name: 'luigi', beltColour: 'brown', age: 35, id: 3},
	]

	const handleClick = (id) => {
		// delete the person from people
		people = people.filter((person) => person.id !== id)
	}

	const toggleModal = () => {
		showModal = !showModal
	}

	const addPerson = (e) => {
		const person = e.detail
		people = [person, ...people]
		showModal = false
	}

</script>

<!-- When prop and variable name are the same can use the shorthand like used here for showModal. -->
<!-- slots: method for passing child content into component.  -->
<Modal {showModal} on:click={toggleModal}>
	<AddPersonForm on:addPerson={addPerson} />
</Modal>

<main>
	<!-- using |once event modifier here. -->
	<button on:click|once={toggleModal}>Open Modal</button>
	{#each people as person (person.id)}
		<div>
			<h4>{person.name}</h4>
			{#if person.beltColour === 'black'}
				<p><strong>Master Ninja</strong></p>
			{/if}
			<p>{person.age} years old, {person.beltColour} belt.</p>
			<button on:click={() => handleClick(person.id)}>Delete</button>
		</div>
	{:else}
		<p>There are no people to show...</p>
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