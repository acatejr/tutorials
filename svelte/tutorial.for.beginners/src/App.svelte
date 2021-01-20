<script>
	/*
	let firstName = 'Jimmy'
	let lastName = 'Hendrix'
	let beltColour = 'brown'
	*/
	let people = [
		{ name: 'yoshi', beltColour: 'black', age: 25, id: 1},
		{ name: 'mario', beltColour: 'orange', age: 45, id: 2},
		{ name: 'luigi', beltColour: 'brown', age: 35, id: 3},
	]

	// // Reactive value
	// $: fullName = `${firstName} ${lastName}`

    // // Reactive statement
	// $: console.log(beltColour)

	// // Reactive statement
	// $: {
	// 	console.log(firstName)
	// 	console.log(lastName)
	// 	console.log(fullName)
	// }

	// const handleClick = () => {
	// 	beltColour = 'green'
	// }

	// const handleInput = (e) => {
	// 	beltColour = e.target.value
	// }

</script>

<main>
	{#each people as person (person.id)}
		<div>
			<h4>{person.name}</h4>
			<p>{person.age} years old, {person.beltColour} belt.</p>
		</div>
	{:else}
		<p>There are no people to show...</p>
	{/each}

	<!--
	<p>{fullName} {beltColour} belt</p>
	<input type='text' bind:value={firstName}>
	<input type='text' bind:value="{lastName}">
	<input type='text' bind:value={beltColour}>
	<button on:click={handleClick}>Update Belt Colour</button>	
	-->
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

	.score {
		width: 35px;
	}
</style>