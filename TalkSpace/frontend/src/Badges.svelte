<script>
    import { Badge } from 'flowbite-svelte';
    export let toggle
    export let sources = []

</script>
<div class=" w-4/5">
    {#each sources as source }
    <Badge href={source['url']} class='text-slate-200 bg-blue-600 hover:bg-sky-600 hover:scale-105 mx-1'>{source['title']}</Badge>
    {/each}
    <!-- <Badge href="/" class='text-slate-200 bg-blue-600 hover:bg-sky-600 hover:scale-105 mx-1'>Sefaria</Badge>
    <Badge href="/" class='text-slate-200 bg-blue-600 hover:bg-sky-600 hover:scale-105 mx-1'>what does being jewish mean</Badge>
    <Badge href="/" class='text-slate-200 bg-blue-600 hover:bg-sky-600 hover:scale-105 mx-1'>lol</Badge>
    <Badge href="/" class='text-slate-200 bg-blue-600 hover:bg-sky-600 hover:scale-105 mx-1'>anyway</Badge>
    <Badge href="/" class='text-slate-200 bg-blue-600 hover:bg-sky-600 hover:scale-105 mx-1'>Badge link</Badge>
    <Badge href="/" class='text-slate-200 bg-blue-600 hover:bg-sky-600 hover:scale-105 mx-1'>Badge link</Badge>
    <Badge href="/" class='text-slate-200 bg-blue-600 hover:bg-sky-600 hover:scale-105 mx-1'>Badge link</Badge>
    <Badge href="/" class='text-slate-200 bg-blue-600 hover:bg-sky-600 hover:scale-105 mx-1'>Badge link</Badge>
    <Badge href="/" class='text-slate-200 bg-blue-600 hover:bg-sky-600 hover:scale-105 mx-1'>Badge link</Badge> -->
    <Badge type="button" class='text-slate-200 bg-purple-600 hover:bg-purple-500 hover:scale-105 mx-1' ><button class="" on:click={()=>{console.log('closed');toggle()}}>sources</button> </Badge>
    </div>