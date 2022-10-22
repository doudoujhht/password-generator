<script>
	export let texte;
	export let cocher;
</script>

<label class="container flex items-center pt-2">
	<input type="checkbox" bind:checked={cocher} />
	<span class="checkmark flex justify-center items-center" />
	<span class="text block pl-6 text-base">{texte}</span>
</label>

<style>
	.text {
		font-size: 00.8em;
	}
	.container {
		/* display: block; */
		position: relative;
		cursor: pointer;
		font-size: 1.3em;
		-webkit-user-select: none;
		-moz-user-select: none;
		-ms-user-select: none;
		user-select: none;
	}

	/* Hide the browser's default checkbox */
	.container input {
		position: absolute;
		opacity: 0;
		cursor: pointer;
		height: 0;
		width: 0;
	}

	/* Create a custom checkbox */
	.checkmark {
		top: 0;
		left: 0;
		height: 0.8em;
		width: 0.8em;
		background-color: #18171f;
		border: 0.1em solid white;
	}

	/* On mouse-over, add a grey background color */

	/* When the checkbox is checked, add a blue background */
	.container input:checked ~ .checkmark {
		background-color: #a4ffaf;
		border: 0.1em solid #a4ffaf;
	}
	.container input:hover ~ .checkmark {
		border: 0.1em solid #a4ffaf;
	}

	/* Create the checkmark/indicator (hidden when not checked) */
	.checkmark:after {
		content: '';
		position: absolute;
		display: none;
	}

	/* Show the checkmark when checked */
	.container input:checked ~ .checkmark:after {
		display: block;
	}

	/* Style the checkmark/indicator */
	.container .checkmark:after {
		width: 0.3em;
		height: 0.5em;
		border: solid #23242c;
		border-width: 0 3px 3px 0;
		-webkit-transform: rotate(45deg);
		-ms-transform: rotate(45deg);
		transform: rotate(45deg);
	}
</style>
