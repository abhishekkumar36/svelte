<script>
	let firstName="Abhishek";
	let lastName="Kumar"
	$:fullName = `${firstName} ${lastName}`
	// $:console.log(beltColor)
	$:{
		// console.log("Hurray")
		console.log(firstName);
		console.log(lastName)
	}
	let beltColor = "black";
	const handleClick = () => {
		beltColor = "orange";
	}
	const handleInput = (e) => {
		beltColor = e.target.value
	}
</script>

<main>
	<h1>{fullName}</h1>
	<h1 style="color:{beltColor}">{beltColor}   belt </h1>
	<!-- <button on:click={handleClick}>update color</button> -->
	<!-- <input type="text" value={beltColor} on:input={handleInput}> -->
	<input type="text" bind:value={firstName}>
	<input type="text" bind:value={lastName}>

	<input type="text" bind:value={beltColor}>
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
</style>