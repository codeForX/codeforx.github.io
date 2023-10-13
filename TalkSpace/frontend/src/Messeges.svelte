<script>
      import { Badge } from 'flowbite-svelte';
    import Badges from './Badges.svelte';
      export let toggle
      export let messages = []

</script>
<div class="p-10 ">

{#each messages as msg }
 {#if msg['role'] == 'User'}
 <h1 class="text-2xl text-blue-300 ">
    {msg['content']}
  </h1>
  {:else}
  <div class="pl-4 text-xl text-gray-300">
    <Badges toggle={toggle} sources={msg['sources']}/>
    <br/>
    <p>
        {msg['content']}
    </p>
    
  </div>
 {/if}
 <br/>

{/each}
<br/>
<br/>
<!-- <h1 class="text-2xl text-blue-300 ">
    What is this page? lor
  </h1>


  <br />
  <div class="pl-4 text-xl text-gray-300">
    <Badges toggle={toggle}/>
    <br/>
    <p>
        Lorem ipsum dolor sit amet consectetur adipisicing elit. Esse id, incidunt soluta distinctio illum odit, molestiae sapiente voluptas officiis non voluptatibus vero fuga eum animi sit dolores maxime atque. Accusantium!
    </p>
    <p>
        Lorem ipsum dolor sit amet consectetur adipisicing elit. Esse id, incidunt soluta distinctio illum odit, molestiae sapiente voluptas officiis non voluptatibus vero fuga eum animi sit dolores maxime atque. Accusantium!
    </p>
    
  </div>
    <br />
  <h1 class="text-2xl text-blue-300 ">
    but really?
  </h1>
  <br />
  <div class="pl-4 text-xl text-gray-300">
    <p>
        Lorem ipsum dolor sit amet consectetur.
    </p>
    <p>
        Sapiente voluptas officiis non voluptatibus vero fuga eum animi sit dolores maxime atque. Accusantium!
    </p>
    
  </div>
    <br />
  <h1 class="text-2xl text-blue-300 ">
    What is this page?
  </h1>
  <br />
  <div class="pl-4 text-xl text-gray-300">
    <p>
        Lorem ipsum dolor sit amet consectetur adipisicing elit. Esse id, incidunt soluta distinctio illum odit, molestiae sapiente voluptas officiis non voluptatibus vero fuga eum animi sit dolores maxime atque. Accusantium!
    </p>
    <p>
        Lorem ipsum dolor sit amet consectetur adipisicing elit. Esse id, incidunt soluta distinctio illum odit, molestiae sapiente voluptas officiis non voluptatibus vero fuga eum animi sit dolores maxime atque. Accusantium!
    </p>
    
  </div>
    <br />
  <h1 class="text-2xl text-blue-300 ">
    but really?
  </h1>
  <br />
  <div class="pl-4 text-xl text-gray-300">
    <p>
        Lorem ipsum dolor sit amet consectetur.
    </p>
    <p>
        Sapiente voluptas officiis non voluptatibus vero fuga eum animi sit dolores maxime atque. Accusantium!
    </p>
    
  </div>
  <br />

  <h1 class="text-2xl text-blue-300 ">
    What is this page?
  </h1>
  <br />
  <div class="pl-4 text-xl text-gray-300">
    <p>
        Lorem ipsum dolor sit amet consectetur adipisicing elit. Esse id, incidunt soluta distinctio illum odit, molestiae sapiente voluptas officiis non voluptatibus vero fuga eum animi sit dolores maxime atque. Accusantium!
    </p>
    <p>
        Lorem ipsum dolor sit amet consectetur adipisicing elit. Esse id, incidunt soluta distinctio illum odit, molestiae sapiente voluptas officiis non voluptatibus vero fuga eum animi sit dolores maxime atque. Accusantium!
    </p>
    
  </div>
    <br />
  <h1 class="text-2xl text-blue-300 ">
    but really?
  </h1>
  <br />
  <div class="pl-4 text-xl text-gray-300">
    <p>
        Lorem ipsum dolor sit amet consectetur.
    </p>
    <p>
        Sapiente voluptas officiis non voluptatibus vero fuga eum animi sit dolores maxime atque. Accusantium!
    </p>
    
  </div>
  <br />

  <h1 class="text-2xl text-blue-300 ">
    What is this page?
  </h1>
  <br />
  <div class="pl-4 text-xl text-gray-300">
    <p>
        Lorem ipsum dolor sit amet consectetur adipisicing elit. Esse id, incidunt soluta distinctio illum odit, molestiae sapiente voluptas officiis non voluptatibus vero fuga eum animi sit dolores maxime atque. Accusantium!
    </p>
    <p>
        Lorem ipsum dolor sit amet consectetur adipisicing elit. Esse id, incidunt soluta distinctio illum odit, molestiae sapiente voluptas officiis non voluptatibus vero fuga eum animi sit dolores maxime atque. Accusantium!
    </p>
    
  </div>
    <br />
  <h1 class="text-2xl text-blue-300 ">
    but really?
  </h1>
  <br />
  <div class="pl-4 text-xl text-gray-300">
    <p>
        Lorem ipsum dolor sit amet consectetur.
    </p>
    <p>
        Sapiente voluptas officiis non voluptatibus vero fuga eum animi sit dolores maxime atque. Accusantium!
    </p>
    
  </div>
  <br /> -->
</div>