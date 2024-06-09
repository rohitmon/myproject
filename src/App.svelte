<script>
	let firstName = 'Rohit';
	let lastName = 'Mondal';
	let beltcolour = 'yellow';

	$: fullName = `${firstName} ${lastName}`

	$: {
		console.log(beltcolour);
		console.log(fullName);
	}

	const handleInput = (e) => {
	    beltcolour = e.target.value;
	}

	const handleClick = () => {
        beltcolour = 'orange';
    }

	let people = [
		{name: 'Yoshi', beltcolour: 'black', age: 24, id : 1},
		{name: 'Rohit', beltcolour: 'orange', age: 25, id : 2},
		{name: 'Raju', beltcolour: 'red', age: 26, id : 3}
	]

</script>

<main>
	{#each people as person (person.id)}
		<div>
			<p>{person.name} - {person.beltcolour} belt</p>
            <button on:click={handleClick}>{person.beltcolour}</button>
            <input type="text" bind:value={person.beltcolour}>
            <input type="text" bind:value={person.name}>
            <input type="text" bind:value={person.age}>
            <input type="text" bind:value={person.id}>
            <br>
		</div>
	{:else}
		<p>No people to show....</p>
	{/each}
</main>

<style>
	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}

	/*h1 {
		color: #ff3e00;
		text-transform: uppercase;
		font-size: 4em;
		font-weight: 100;
	}*/

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>