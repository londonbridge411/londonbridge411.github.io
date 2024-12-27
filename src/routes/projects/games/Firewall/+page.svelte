<script lang="ts">
    import clickOutside from "$lib/clickOutside";
    import Firewall from '$lib/assets/images/covers/Firewall.png';
    
	import { onDestroy, onMount } from "svelte";

    onMount(() => {
        let elem = document.getElementById("bg-image") as HTMLElement;
        
        elem.style.backgroundImage = "url(" + Firewall + ")";
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

<h1 class="title">Firewall</h1>
<div class="blur" />

<div use:clickOutside on:click_outside={GoBack} id="test" class="project-page-container">
    <div class="main-image" >
        <iframe class = "actual-picture" width="640" height="360" src="https://www.youtube.com/embed/ApzTZ1-kAcs" title="YouTube video player"
        frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
        allowfullscreen></iframe>
        <p class="context">A trailer for the WVU Student Organization Fair.</p>
    </div>

    <hr />
    

    <h2 class="subtitle">Description</h2>
    <p class="regular-text">Firewall is top-down shooter that takes elements from classics such as Dark Souls, Zelda, and DOOM.
        The player is tasked with eleminating viruses within the system. The player will explore many different locales ranging
        from abandoned towns and lush digital forests to transforming labyrinths and dangerous castles. The player will gain
        abilities and weapons to better take on these locations.
    </p>

    <h2 class="subtitle">Contributions</h2>
    <ul>
        <li>Working as a solo developer.</li>
        <li>Composed the music.</li>
        <li>Programmed player movement, shooting, and dodging.</li>
        <li>Programmed enemy AI.</li>
        <li>Programmed the inventory system.</li>
        <li>Programmed a Save/Load System.</li>
        <li>Created the ceiling fade and it's shader.</li>
        <li>Created all of the UI.</li>
        <li>Implemented Object Pooling.</li>
    </ul>

    <h2 class="subtitle">Media</h2>
</div>
