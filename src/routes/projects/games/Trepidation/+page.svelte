<script lang="ts">
    import clickOutside from "$lib/clickOutside";
        
    import TrepidationTitle from "$lib/assets/images/backgrounds/TrepidationTitle.png";
    import LivingRoom from "$lib/assets/images/covers/trep.png"
	import { onDestroy, onMount } from "svelte";
	import Customimage from "$lib/components/customimage.svelte";

    import trep2 from "$lib/assets/images/other/trep2.png";
    import trep3 from "$lib/assets/images/other/trep3.png";

    onMount(() => {
        let elem = document.getElementById("bg-image") as HTMLElement;
        
        elem.style.backgroundImage = "url(" + LivingRoom + ")";
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


<h1 class="title">Trepidation</h1>
<div class="blur" />

<div use:clickOutside on:click_outside={GoBack} id="test" class="project-page-container">
    <div class="main-image" >
        <img src={TrepidationTitle} />
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
    <h2 class="subtitle">Details</h2>
    <ul>
        <li>Started in 2022 during my Junior/Senior year of college.</li>
        <li>Built in Unity 6 using C#.</li>
        <li>Using Unity Netcode for GameObjects, FacePunch, and SteamMatchmaking for multiplayer.</li>
    </ul>
    <h2 class="subtitle">Contributions</h2>
    <ul>
        <li>Working as the lead developer.</li>
        <li>Currently implementing a FSM-GOAP-Hybrid AI for the singleplayer mode.</li>
        <li>Implemented multiplayer networking through Steamworks, Facepunch, and Unity's Netcode for GameObjects.</li>
        <li>Implemented Steam lobbies into the game.</li>
        <li>Progammed many of the basic gameplay mechanics such as: opening/closing doors, flipping lightswitches, etc.</li>
        <li>Programmed the lightbulb/breaker system.</li>
        <li>Programmed the item pickup, rotate, and throwing system.</li>
        <li>Programmed all of the ghost mechanics such as: placing traps, trap cooldown, and specific ghost abilities.</li>
        <li>Implemented some video and audio settings that are saved.</li>
        <li>Designed and textured the entire house scene (the one shown in images).</li>
        <li>Designed and created the main menu.</li>
        <li>Designed the main logo.</li>
        <li>Handled all of the post-processing and graphical optimizations.</li>
    </ul>
    <h2 class="subtitle">Media</h2>

    <div class="media-holder">
        <Customimage src={TrepidationTitle} width=350 text="Title screen." />
        <Customimage src={LivingRoom} width=350 text="Living room in the Demo House as a player." />
        <Customimage src={trep2} width=350 text="Staircase in the Demo House as the ghost." />
        <Customimage src={trep3} width=350 text="Bathroom in the Demo House as the ghost." />
    </div>

</div>
