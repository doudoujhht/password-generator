<script>
    import PartieHaute from "./partie-haute.svelte";
    import PartieBasse from "./partie-basse.svelte";
</script>

<div class="w-[95%] sm:w-3/4 md:w-[70%] lg:w-3/6 xl:w-2/5 2xl:w-1/3">
    <PartieHaute/>
    <PartieBasse/>
</div>
<style>
    @font-face{
  font-family: 'JetBrainsMono';
  src: url('https://cdn.jsdelivr.net/gh/JetBrains/JetBrainsMono/web/woff2/JetBrainsMono-Regular.woff2') format('woff2'),
    url('https://cdn.jsdelivr.net/gh/JetBrains/JetBrainsMono/web/woff/JetBrainsMono-Regular.woff') format('woff'),
    url('https://cdn.jsdelivr.net/gh/JetBrains/JetBrainsMono/ttf/JetBrainsMono-Regular.ttf') format('truetype');
  font-weight: 400;
  font-style: normal;
}
</style>