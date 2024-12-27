<script lang="ts">
    import clickOutside from "$lib/clickOutside";
    import "$lib/styles/text.css";
    import "$lib/styles/project-page.css"
    
    import UmuseBG from "$lib/assets/images/umuse/umuse2.png";
    import UmuseCover from "$lib/assets/images/umuse/umuse1.png";
    import UmuseDiscover from "$lib/assets/images/umuse/umuse3.png";
    import UmuseArtists from "$lib/assets/images/umuse/umuse4.png";
    import UmusePlaylists from "$lib/assets/images/umuse/umuse5.png";
    import UmuseEditPlaylist from "$lib/assets/images/umuse/umuse6.png";
    import UmuseQueue from "$lib/assets/images/umuse/umuse7.png";


	import { onDestroy, onMount } from "svelte";
	import Customimage from "$lib/components/customimage.svelte";

    

    onMount(() => {
        let elem = document.getElementById("bg-image") as HTMLElement;
        
        elem.style.backgroundImage = "url(" + UmuseBG + ")";
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
        <img src={UmuseCover} />
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
    <div class="media-holder">
        <Customimage src={UmuseBG} text="Image of the Firewall OST." />
        <Customimage src={UmuseDiscover} text="Image of the Discover page." />
        <Customimage src={UmuseArtists} text="Image of the subscribed artists page." />
        <Customimage src={UmusePlaylists} text="Image of my account's created and subscribed playlists." />
        <Customimage src={UmuseEditPlaylist} text="Image of me editing a playlist." />
        <Customimage src={UmuseQueue} text="Image of the queue." />
    </div>
</div>
