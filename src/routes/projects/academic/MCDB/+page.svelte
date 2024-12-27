<script lang="ts">
    import clickOutside from "$lib/clickOutside";

    import TrepidationBG from "$lib/assets/images/backgrounds/TrepidationTitle.png";
	import { onDestroy, onMount } from "svelte";

    onMount(() => {
        let elem = document.getElementById("bg-image") as HTMLElement;
        
        elem.style.backgroundImage = "url(" + TrepidationBG + ")";
        elem.classList.add("bg-fade-in");			
        elem.classList.remove("bg-fade-out");	
    })

    onDestroy(() => {
    //     let elem = window.document.getElementById("bg-image") as HTMLElement;
    //     elem.style.backgroundImage = "";
    //     elem.classList.add("bg-fade-out");			
    //     elem.classList.remove("bg-fade-in");	
    })

    function GoBack(event: Event)
    {
        window.history.back();
    }

</script>

<svelte:document  />

<h1 class="title">Trepidation</h1>
<div class="blur" />

<div use:clickOutside on:click_outside={GoBack} id="test" class="project-page-container">
    <div class="main-image" >
        <img src={TrepidationBG} />
        <p class="context">Image of current title screen</p>
    </div>

    <hr />
    

    <h2 class="subtitle">Description</h2>
    <p class="regular-text">Trepidation is a first-person asymmetrical horror game where a group of players
        try to vanquish one player-controlled ghost. The goal of the ghost is to stop the hunters in their
        tracks by setting traps, screaming, and even transporting them to different dimensions. The game will
        boast a multitude of maps with varying objects each playthrough and multiple ghost types to choose from.
        Currently, we are developing a demo to showcase. The demo will include 1 ghost type, 1 map, and a few sets
        of random objectives.
    </p>

    <h2 class="subtitle">Contributions</h2>
    <h2 class="subtitle">Media</h2>
</div>
