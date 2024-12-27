<script lang="ts">
    import clickOutside from "$lib/clickOutside";

    
    import UmusePlaylist from "$lib/assets/images/umuse/umuse2.png";
    import UmuseFullscreen from "$lib/assets/images/umuse/umuse8.png";
    import UmuseAccount from "$lib/assets/images/umuse/umuse1.png";
    import UmuseDiscover from "$lib/assets/images/umuse/umuse3.png";
    import UmuseArtists from "$lib/assets/images/umuse/umuse4.png";
    import UmusePlaylists from "$lib/assets/images/umuse/umuse5.png";
    import UmuseEditPlaylist from "$lib/assets/images/umuse/umuse6.png";
    import UmuseQueue from "$lib/assets/images/umuse/umuse7.png";


	import { onDestroy, onMount } from "svelte";
	import Customimage from "$lib/components/customimage.svelte";

    

    onMount(() => {
        let elem = document.getElementById("bg-image") as HTMLElement;
        
        elem.style.backgroundImage = "url(" + UmuseFullscreen + ")";
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

<h1 class="title">uMuse</h1>
<div class="blur" />

<div use:clickOutside on:click_outside={GoBack} id="test" class="project-page-container">
    <div class="main-image" >
        <img src={UmusePlaylist} />
        <p class="context">Image of the Firewall OST.</p>
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

    <h2 class="subtitle">Details</h2>
    <ul>
        <li>Started in Fall 2023.</li>
        <li>~85% completion. Currently taking a break to work on other projects.</li>
        <li>Built using React, NodeJS, and Supabase.</li>
        <li>Uses React Redux for state management.</li>
        <li>Supports mobile.</li>
    </ul>

    <h2 class="subtitle">Media</h2>
    <div class="media-holder">
        <Customimage src={UmuseFullscreen} width=350 text="Image of a song playing in Fullscreen Mode." />
        <Customimage src={UmuseAccount} width=350 text="Image of londythehammer's account." />
        <Customimage src={UmuseDiscover} width=350 text="Image of the Discover page." />
        <Customimage src={UmuseArtists} width=350 text="Image of the subscribed artists page." />
        <Customimage src={UmusePlaylists} width=350 text="Image of my account's created and subscribed playlists." />
        <Customimage src={UmuseEditPlaylist} width=350 text="Image of me editing a playlist." />
        <Customimage src={UmuseQueue} width=350 text="Image of the queue." />
    </div>
</div>
