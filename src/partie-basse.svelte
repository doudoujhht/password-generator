<script>
	import Input from './input.svelte';
	import Checkbox from './checkbox.svelte';
	import Input2 from './input2.svelte';
	import Button from './button.svelte';

	export let mdp;
	let majuscule = false;
	let miniscule = false;
	let nombre = false;
	let symbols = false;
	let valeur = 8;
	export let note = 0;
	const upper = 'ABCDEFGHIJKLMNOPQRSTUVWXYZ';
	const lower = 'abcdefghijklmnopqrstuvwxyz';
	const numbers = '0123456789';
	const Character = '#|!$%&?&*()_-=+';
	const generer = () => {
		note = 0;
		let chaine = '';
		let password = '';

		if (majuscule) {
			chaine += upper;
			note += 0.5;
		}
		if (miniscule) {
			chaine += lower;
			note += 0.5;
		}
		if (nombre) {
			chaine += numbers;
			note += 0.5;
		}
		if (symbols) {
			chaine += Character;
			note += 0.5;
		}
		note += valeur / 10;
		note = Math.round(note);
		if (valeur <= 4) {
			note = 1;
		} else if (valeur < 8) {
			note = 2;
		}
		console.log(note);

		if (chaine == '') {
			alert('selectionnez au moins un type de caractere');
		} else {
			for (let i = 0; i < valeur; i++) {
				password += chaine.charAt(
					Math.floor(Math.random() * chaine.length)
				);
			}
			mdp = password;
		}
	};
</script>

<div
	class="w-full px-4 py-2 text-white bg-[#24232c] mt-5 font-['JetBrainsMono']"
>
	<div class="flex justify-between text-xl">
		<span>Character Length</span>
		<span>{valeur}</span>
	</div>

	<div>
		<Input bind:value={valeur} />
		<Checkbox texte="Include Uppercase Letters" bind:cocher={majuscule} />
		<Checkbox texte="Include Lowercase Letters" bind:cocher={miniscule} />
		<Checkbox texte="Include Numbers" bind:cocher={nombre} />
		<Checkbox texte="Include Symbols" bind:cocher={symbols} />
		<Input2 bind:note />
		<Button on:click={generer} />
	</div>
</div>
