<script>
	let name = "ge";
	let age = 30;

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

	function defaultName() {
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
<button type="text"  on:click="{defaultName}">DefaultName</button>
<input type="text" value="{name}" on:input="{replaceName}">
