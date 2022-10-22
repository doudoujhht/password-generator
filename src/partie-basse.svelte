<script>
    import Input from "./input.svelte";
    import Checkbox from "./checkbox.svelte";
    import Input2 from "./input2.svelte";
    import Button from "./button.svelte";
</script>
<div class="w-full px-4 py-2 text-white bg-[#24232c] mt-5 font-['JetBrainsMono']">
    <div class="flex justify-between text-xl">
        <span>Character Length</span>
        <span>0</span>
    </div>

    <div>
        <Input/>
        <Checkbox texte="Include Uppercase Letters"/>
        <Checkbox texte="Include Lowercase Letters"/>
        <Checkbox texte="Include Numbers"/>
        <Checkbox texte="Include Symbols"/>
        <Input2/>
        <Button/>

    </div>
</div>
