<script>
	import { text } from 'svelte/internal';

	let classes = 'border-solid border-[1px] border-white h-5 w-2 ml-1 ';
	export let note;
	let nouvelleClasse = '';
	let texte = '';
	$: {
		if (note > 4) note = 4;
		if (note == 1) {
			nouvelleClasse = 'bg-[#f64a4a] border-[#f64a4a]';
			texte = 'too low';
		} else if (note == 2) {
			nouvelleClasse = 'bg-[#fb7c58] border-[#fb7c58]';
			texte = 'low';
		} else if (note == 3) {
			nouvelleClasse = 'bg-[#f8cd65] border-[#f8cd65]';
			texte = 'medium';
		} else if (note == 4) {
			nouvelleClasse = 'bg-[#a4ff45] border-[#a4ff45]';
			texte = 'perfect';
		}
		console.log(note);
		console.log();
	}
</script>

<div class="h-11 flex justify-between items-center bg-[#18171f] px-5 mt-6">
	<div class="uppercase text-[#817d92] font-bold">strength</div>
	<div class="uppercase flex">
		<span class="pr-2">{texte}</span>

		{#each Array(note) as element, index (index)}
			<div class="{classes}{nouvelleClasse}" />
		{/each}
		{#each Array(4 - note) as element, index (index)}
			<div class={classes} />
		{/each}
	</div>
</div>
