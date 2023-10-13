<script>
    export let invisible;
    export let width;
</script>

<div class="fixed bottom-0 py-4 bg-slate-900   px-8  {width} "> <!-- Add w-full to span the full width of the viewport -->
    <div class="flex bg-gray-800 rounded mx-auto"> <!-- Add mx-auto to center it -->
      <span class="p-4 text-gray-400">
        🔍
      </span>
      <input class="flex-1 p-4 bg-transparent outline-none text-white rounded-r" type="text" placeholder="Send a message">
      <span class="p-4 text-gray-400">
        ➤
      </span>
    </div>
  </div>
  

  <style lang="postcss">
    :global(html) {
      background-color: theme(colors.gray.100);
    }
    .hamburger, .close-icon {
      font-size: 24px;
    }
    /* .custom-inset-x {
        left: calc(20rem);
        right: calc(0rem);
    } */
  </style>
  