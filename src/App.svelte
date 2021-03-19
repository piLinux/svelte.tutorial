<script>
	import ContactCard from "./ContactCard.svelte";

	let name = 'Max';
	let age = 30;
	let jobTitle = 'Job Title';
	let userImage = 'https://cdn.pilinux.me/images/GoREST/logo/GoREST-Logo.png';
	let description = 'Description';

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

	function inputName(event) {
		const inputValue = event.target.value;
		name = inputValue;
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
<hr><br>

<!-- updates name with every keystroke -->
<input type="text" value="{name}" on:input="{inputName}">
<br>
<!-- two-way binding shortcut -->
<input type="text" bind:value="{name}">
<br>
<br>

<input type="text" bind:value="{jobTitle}">
<br>
<input type="text" bind:value="{userImage}">
<br>
<input type="text" bind:value="{description}">

<!-- example: self-extending properties -> description="{description}" -->
<ContactCard
userName="{name}"
jobTitle="{jobTitle}"
userImage="{userImage}"
{description}
/>
