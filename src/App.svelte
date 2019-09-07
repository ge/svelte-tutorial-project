<script>
	import CC from "./ContactCard.svelte";

	let name = "ge";
	let title = "Technical Lead";
	let desc = "Do the important work.";
	let age = "";
	let userImage = "";

	$: upperCaseName=name.toUpperCase();
	$: console.log(name);
	$: if (name === "ge") {
		console.log("found expected name");
		age = 76;
	} else {
		console.log("did not find expected name");
	}

	function incrementAge() {
		age += 1;
	}

	/* Not really deprecated.  This will work if needed. */
	function deprecatedDefaultName() {
		name = "zabouti";
	}

	function replaceName(event) {
		name = event.target.value;
	}

</script>

<style>
	h1 {
		color: purple;
	}
</style>

<h1>Hello {name}!</h1>

<h2>Button action</h2>
<p>This example (and its associated function) have been deprecated because the value is hardwired.</p>
<button type="text"  on:click="{deprecatedDefaultName}">DefaultName (Deprecated)</button>

<h2>Form input</h2>
<p>This first input field works just fine, but it's more verbose internally than the following example.</p>
<input type="text" value="{name}" on:input="{replaceName}">
<p>This input field uses svelte keyword <em>bind</em>, which replaces the function needed in the first input field.  This is very clever.</p>
<input type="text" bind:value="{name}">

<h1>Fill in Current Contact Card Component</h1>

<div>Name: </div>				<input type="text" bind:value="{name}">
<div>Job Title: </div>		<input type="text" bind:value="{title}">
<div>User Image URL: </div>	<input type="text" bind:value="{userImage}">
<br />
<div>Job Description: </div>
<textarea rows="3" bind:value="{desc}"></textarea>

<!-- This is one-way communication.  E.g., the value of CC:jobTitle does not affect APP:title -->
<CC userName="{name}" jobTitle="{title}" description="{desc}" userImageURL="{userImage}"/>
