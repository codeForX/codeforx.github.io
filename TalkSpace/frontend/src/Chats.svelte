<script>
    export let chats =[];
    export let activated = 0;
    
    
  </script>
  <ul class={`text-white p-4`}>
    {#each chats as chat, index}
    <button class="text-white my-2 py-2 rounded-md mr-4 transition-transform transform hover:scale-105 w-full  hover:bg-sky-600 {index==activated? 'bg-sky-900':''} " on:click={()=>{activated=index}}>
      {chat}
    </button>
    {/each}
  </ul>
  