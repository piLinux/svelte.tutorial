<script>
	let name = 'Max';
	let age = 30;

	// let upperCaseName; => not required
	$: upperCaseName = name.toUpperCase();

	// output in browser's console
	$: console.log(name);

	// executed ONLY when the name is changed
	$: if (name === 'Maximus') {
		console.log('Button clicked!');
		age = 35;
	}

	function incrementAge() {
		age += 1;
	}

	function changeName() {
		name = 'Maximus';
	}
</script>

<style>
	h1 {
		color: purple;
	}
</style>

<h1>Hello {upperCaseName}, my age is {age}!</h1>
<button on:click="{incrementAge}">Change Age</button>
<button on:click="{changeName}">Change Name</button>
