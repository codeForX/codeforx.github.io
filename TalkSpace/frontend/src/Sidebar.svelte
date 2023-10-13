<script>
    export let width;
    import settings from './settings.png';
</script>

<div class={`bg-sky-950 top-0 h-full ${width == 'w-0'? 'hidden':''} `}> 
    <h1 class="text-white  pt-4 text-8xl text-center transition-transform transform hover:scale-105 hover:cursor-pointer select-none hover:text-transparent hover:bg-clip-text hover:bg-gradient-to-br hover:from-blue-400 hover:to-purple-600 ">ל.<span class="text-5xl">ai</span></h1>

    <slot></slot>

    <div class="fixed bottom-0  w-3/12  "> <!-- Adjusted padding for the container -->
        <button class=" transition-transform transform px-4 py-10 hover:bg-sky-600 w-full text-white   bg-gradient-to-br from-sky-800 to-purple-600  hover:from-purple-500 hover:to-sky-700" on:click={()=>{activated=index}}>
            <p>upgrade to premium</p>

        </button>
        <button class="transition-transform transform  p-4 hover:bg-sky-600 w-full bg-gray-800 text-white" on:click={()=>{activated=index}}>
            Sruly Rosenblat
            <!-- <img src={settings} class="inline-block w-4 h-4 ml-2" /> -->
        </button>
    </div>
</div>
