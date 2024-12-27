<script lang="ts">
    import clickOutside from "$lib/clickOutside";

    
    import MHIT_AddPage from "$lib/assets/images/mhit/mhit-addpage.png";
    import MHIT_Devices from "$lib/assets/images/mhit/mhit-devices.png";
    import MHIT_Edit from "$lib/assets/images/mhit/mhit-edit.png";
    import MHIT_Home from "$lib/assets/images/mhit/mhit-home.png";
    import MHIT_Printer from "$lib/assets/images/mhit/mhit-printer.png";
    import MH_BG from "$lib/assets/images/mhit/mh.jpg";

	import { onDestroy, onMount } from "svelte";
	import Customimage from "$lib/components/customimage.svelte";

    onMount(() => {
        let elem = document.getElementById("bg-image") as HTMLElement;
        
        elem.style.backgroundImage = "url(" + MH_BG + ")";
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


<h1 class="title">Marshall Health IT Docs</h1>
<div class="blur" />

<div use:clickOutside on:click_outside={GoBack} id="test" class="project-page-container">
    <div class="main-image" >
        <img src={MHIT_Home} />
        <p class="context">Image of current homepage.</p>
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
    <h2 class="subtitle">Details</h2>
    <ul>
        <li>Started in Fall of 2024.</li>
        <li>Development took roughly 1.5 months.</li>
        <li>Built using SvelteKit and MongoDB Atlas</li>
        <li>Anyone on our team has the ability to upload new directories/pages.</li>
        <li>Supports mobile.</li>
    </ul>
    <h2 class="subtitle">Media</h2>
    <div class="media-holder">
        <Customimage src={MHIT_AddPage} width=350 text="Image of a song playing in Fullscreen Mode." />
        <Customimage src={MHIT_Devices} width=350 text="Image of londythehammer's account." />
        <Customimage src={MHIT_Edit} width=350 text="Image of the Discover page." />
        <Customimage src={MHIT_Printer} width=350 text="Image of the subscribed artists page." />
    </div>
</div>
