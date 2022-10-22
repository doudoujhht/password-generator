<script>
	import Input from './input.svelte';
	import Checkbox from './checkbox.svelte';
	import Input2 from './input2.svelte';
	import Button from './button.svelte';

	let majuscule = false;
	let miniscule = false;
	let nombre = false;
	let symbols = false;
    let valeur=14;
	$:{
		console.log(valeur)
	}

	let text = 'Include Uppercase Letters';

	const test=()=>{
		console.log(valeur)
		if(majuscule){
			console.log("majuscule")
		}
	}
	const generer = () => {
		const Character =
			'ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz0123456789#|!$%&?&*()_-=+';
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
		<Input bind:value={valeur}/>
		<Checkbox texte={text} bind:cocher={majuscule} />
		<Checkbox texte="Include Lowercase Letters" bind:cocher={miniscule} />
		<Checkbox texte="Include Numbers" bind:cocher={nombre} />
		<Checkbox texte="Include Symbols" bind:cocher={symbols} />
		<Input2 />
		<Button on:click={test}/>
	</div>
</div>
