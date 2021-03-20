<script>
	import ContactCard from "./ContactCard.svelte";

	let name = 'Max';
	let age = 30;
	let jobTitle = 'Job Title';
	let userImage = 'https://cdn.pilinux.me/images/GoREST/logo/GoREST-Logo.png';
	let description = 'Description';
	
	let done = false;

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

	function createCard() {
		done = true;
	}
</script>

<style>
	h1 {
		color: purple;
	}
	
	#form {
		width: 30rem;
		max-width: 100%;
	}
</style>

<h1>Hello {upperCaseName}, my age is {age}!</h1>
<button on:click="{incrementAge}">Change Age</button>
<button on:click="{changeName}">Change Name</button>
<hr><br>

<div id="form">
	<div class="form-control">
		<label for="userName">User Name</label><br>
		<input type="text" bind:value={name} id="userName" />
	</div>
	<br>
	<div class="form-control">
		<label for="jobTitle">Job Title</label><br>
		<input type="text" bind:value={jobTitle} id="jobTitle" />
	</div>
	<br>
	<div class="form-control">
		<label for="image">Image URL</label><br>
		<input type="text" bind:value={userImage} id="image" />
	</div>
	<br>
	<div class="form-control">
		<label for="desc">Description</label><br>
		<textarea rows="3" bind:value={description} id="desc" />
	</div>
</div>
<br>

<button on:click="{createCard}">Create Card</button>

{#if done}
<hr>
<br>
<!-- example: self-extending properties -> description="{description}" -->
<ContactCard
userName="{name}"
jobTitle="{jobTitle}"
userImage="{userImage}"
{description}
/>
{/if}
