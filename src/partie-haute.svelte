<script>
	import Icon from './Icon.svelte';
	export let texte;
	let color = '#a4ffaf';
	let copied = '';
	const copier = () => {
		navigator.clipboard.writeText(texte);
		copied = 'copied!';
	};
</script>

<div
	class="flex bg-[#24232c] h-12 justify-between items-center pr-1 pl-4 py-8 text-white w-full font-['JetBrainsMono']"
>
	<input
		type="text"
		class="bg-[#24232c] h-11 w-[91%] focus:outline-0 text-3xl  flex items-center"
		placeholder="P4$5W0rD"
		bind:value={texte}
	/>
	<Icon {texte} bind:copied on:click={copier} />
</div>
