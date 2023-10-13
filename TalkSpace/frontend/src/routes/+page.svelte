<script>
    import Sidebar from '../Sidebar.svelte';
    import SearchBar from '../SearchBar.svelte';
    import Chats from '../Chats.svelte';
    import Messeges from '../Messeges.svelte';
    import SendMessage from '../SendMessage.svelte';
  
    let sidebarhidden = writable(false);
    let sourceSheetHidden = writable(false);
    let chats = writable(["Who is moses", "look a keyboard lorem iomsdas fdsfas as fdasas asddsa ", "greetings"]);
    let messages = writable(
        [
            {'role':'User', 'content': 'Hello, how are you?',},
            {'role':'AI', 'content': 'I am doing well, thank you for asking. How can I assist you today?', 'sources':[]},
            {'role':'User', 'content': 'Can you tell me about the history of Hanukkah?',},
            {'role':'AI', 'content': 'Of course! Hanukkah commemorates the rededication of the Second Temple in Jerusalem during the second century BCE. It is also known as the Festival of Lights and is celebrated for eight days and nights. Would you like me to look up more information?', 'sources':[{'url':'https://www.history.com/topics/holidays/hanukkah','title':'Hanukkah','website title':'History'}]},
            {'role':'User', 'content': 'Yes, please.',},
            {'role':'AI', 'content': 'The holiday celebrates the victory of the Maccabees over the Greek army and the rededication of the Temple in Jerusalem. According to tradition, when the Maccabees entered the Temple, they found only enough oil to light the menorah for one day. Miraculously, the oil lasted for eight days, which is why Hanukkah is celebrated for eight days and nights.', 'sources':[{'url':'https://www.myjewishlearning.com/article/hanukkah-history/','title':'Hanukkah: History and Significance','website title':'My Jewish Learning'},{'url':'https://www.chabad.org/library/article_cdo/aid/102911/jewish/The-History-of-Hanukkah.htm','title':'The History of Hanukkah','website title':'Chabad.org'}]},
            {'role':'User', 'content': 'Thank you!',},
            {'role':'AI', 'content': 'You\'re welcome! Is there anything else you would like to know?', 'sources':[]},
        ]
    )
    let activated = 0

  
    function toggleSidebar() {
      $sidebarhidden = !$sidebarhidden;
    }
    function toggleSourceSheet() {
      $sourceSheetHidden = !$sourceSheetHidden;
    }
    import { onMount } from 'svelte';
    import { writable } from 'svelte/store';
    import SourceSheet from '../SourceSheet.svelte';
    import Intro from '../Intro.svelte';
    $: console.log($sourceSheetHidden);
  
  const width = writable(0);
  const height = writable(0);
  const scrollable = writable(false); // New state
  const layout = writable('justSidebar');
  const data = {
    'sidebar': ' w-3/12',
    'messages': 'w-6/12',
    'sourceSheets': 'w-3/12'
  };
  const layouts = {
    'allOpen': {
      'sidebar': 'w-3/12',
      'messages': 'w-6/12',
      'sourceSheets': 'w-3/12'
    },
    'mobile': {
      'sidebar': 'w-0',
      'messages': 'w-full',
      'sourceSheets': 'w-0'
    },
    'justSidebar': {
      'sidebar': 'w-3/12',
      'messages': 'w-9/12',
      'sourceSheets': 'w-0'
    }
  }

  onMount(() => {
    if (typeof window !== 'undefined') {
      width.set(window.innerWidth);
      height.set(window.innerHeight);

      const updateSize = () => {
        width.set(window.innerWidth);
        height.set(window.innerHeight);
      };

      window.addEventListener('resize', updateSize);
      return () => window.removeEventListener('resize', updateSize);
    }
    const container = document.querySelector('.scroll-container');
    container.addEventListener('scroll', () => {
      if (container.scrollTop < container.scrollHeight - container.clientHeight) {
        scrollable.set(true);
      } else {
        scrollable.set(false);
      }
    });

  });
    let isMobile = false;

    $: isMobile = $width < 768;
    // $: sidebarhidden = isMobile ? true : false;
    $:{
    if (isMobile) {
      layout.set('mobile');
      
    }
    else if ($sourceSheetHidden)
    {
        layout.set('justSidebar');
    }
    else
    {
        layout.set('allOpen');
    }
}

  </script>

<body class="h-screen overflow-hidden bg-slate-900  ">
    <div class="flex h-full w-full">
        
      <div class=" bg-blue-500 h-full {layouts[$layout]['sidebar']}"> 
        <!-- {sidebarhidden? 'w-0 hidden':'w-3/12'}  -->
        <Sidebar  width={layouts[$layout]['sidebar']}>
            <SearchBar    />
            <Chats chats={$chats}  activated={activated}   />
          </Sidebar>
      </div>
  
      <div class="h-full overflow-y-auto  overscroll-contain {layouts[$layout]['messages']} scrollbar-hide">
        <!--{sidebarhidden? 'w-full':'w-9/12'}  -->
        {#if $messages.length == 0}

        <Intro />
        {:else}
        <Messeges toggle={toggleSourceSheet} messages={$messages}/>
            
        {/if}
        
           
        <SendMessage invisible={sidebarhidden} width={layouts[$layout]['messages']} />        

      </div>
      
      <div class="h-full overflow-y-auto  overscroll-contain {layouts[$layout]['sourceSheets']} scrollbar-hide">
        <!--{sidebarhidden? 'w-full':'w-9/12'}  -->
        <SourceSheet toggle={toggleSourceSheet}/>

      </div>

    
    </div>
  
  </body>

  <style lang="postcss">
    :global(html) {
      background-color: theme(colors.gray.100);
    }
    .hamburger, .close-icon {
      font-size: 24px;
    }
    .custom-inset-x {
        left: calc(18rem);
        right: calc(0rem);
    }
    /* .scroll-arrow {
    position: absolute;
    bottom: 100%;
    left: 50%;
    z-index: 10;

  } */
  </style>
  