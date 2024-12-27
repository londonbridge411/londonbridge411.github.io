<script lang="ts">
    import clickOutside from "$lib/clickOutside";
    import "$lib/styles/text.css";
    import "$lib/styles/project-page.css"
    
    import TrepidationBG from "$lib/assets/images/backgrounds/TrepidationTitle.png";
	import { onDestroy, onMount } from "svelte";

    onMount(() => {
        let elem = document.getElementById("bg-image") as HTMLElement;
        
        elem.style.backgroundImage = "url(" + TrepidationBG + ")";
        elem.classList.add("bg-fade-in");			
        elem.classList.remove("bg-fade-out");	
    })

    onDestroy(() => {
        // let elem = window.document.getElementById("bg-image") as HTMLElement;
        // elem.style.backgroundImage = "";
        // elem.classList.add("bg-fade-out");			
        // elem.classList.remove("bg-fade-in");	
    })

    function GoBack(event: Event)
    {
        window.history.back();
    }

</script>

<svelte:document  />

<h1 class="title">Marshall Health IT Docs</h1>
<div class="blur" />

<div use:clickOutside on:click_outside={GoBack} id="test" class="project-page-container">
    <div class="main-image" >
        <img src={TrepidationBG} />
        <p class="context">Image of current title screen</p>
    </div>

    <hr />
    

    <h2 class="subtitle">Description</h2>
    <p class="regular-text">The Marshall Health IT Docs (AKA MHIT Knowledge Base) is a website 
        powered by NodeJS and SvelteKit built purely by me. It uses MongoDB Atlas for it's database. It provides
         documentation on our processes and solutions to problems. It acts as a guide for new hires and will be
          used to help facilate the merge between Marshall Health and Marshall Health Network.
    </p>
    <p class="regular-text">The site has been built to be expandable without me there. Pages and directories
        can easily be created and added to the database. Pages in particular are very customizable as their
         content uses the TipTap editor with custom features. It supports images, links, and text formatting
          to allow more dynamic and accessible pages.
    </p>
    <p>
        Additionally, the site has a built in system for tracking checked-in devices and loaners. This has helped our
         team better keep track of what devices we are working on and communicate with owner(s) easier.
    </p>
    <h2 class="subtitle">Contributions</h2>
    <h2 class="subtitle">Media</h2>
</div>
