<script>
    export let toggle;
  </script>
  <div class="h-full w-full p-8 ">
    
  <div class={`bg-slate-800  top-0   h-full  rounded-lg overflow-y-auto  scrollbar-hide p-5 break-all`}> 
    <div class="w-full flex justify-between items-center">
        <h1 class="text-lg text-white">sources</h1>
    
        <button class="text-white">
            <div class={`close-icon transition-transform transform hover:scale-125 hover:text-red-300 text-xl`} on:click={()=>{console.log('closed');toggle()}}>
                &times;
            </div>
        </button>
    </div>
    <br/>
    
    <h1 class="text-xl text-white">What is kosher</h1>
    <a class=" text-cyan-500 text-sm">Sefaria</a>
    <p class="text-white text-md"> 
    Kosher is a term used to describe food that complies with the strict dietary standards of traditional Jewish law.
    </p>
    <p class="text-white text-md"> 
        ...
    </p>
    <p class="text-white text-md"> 
        Kosher is a term used to describe food that complies with the strict dietary standards of traditional Jewish law.
    </p>
    <br/>
    <h1 class="text-xl text-white">What is kosher lol looool lool</h1>
    <a class=" text-cyan-500 text-sm">Sefaria</a>
    <p class="text-white text-md"> 
    Kosher is a term used to describe food that complies with the strict dietary standards of traditional Jewish law.
    </p>
    <br/>
    <h1 class="text-xl text-white">What is kosher lol looool lool</h1>
    <a class=" text-cyan-500 text-sm">Sefaria</a>
    <p class="text-white text-md"> 
    Kosher is a term used to describe food that complies with the strict dietary standards of traditional Jewish law.
    </p>
    <br/>
    <h1 class="text-xl text-white">What is kosher lol looool lool</h1>
    <a class=" text-cyan-500 text-sm">Sefaria</a>
    <p class="text-white text-md"> 
    Kosher is a term used to describe food that complies with the strict dietary standards of traditional Jewish law.
    </p>



    <slot></slot>
  </div>
</div>
  