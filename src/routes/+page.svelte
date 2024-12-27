<script lang="ts">
	import { fade } from 'svelte/transition';
    import { goto } from "$app/navigation";
	import Navbar from "$lib/components/navbar.svelte";
	import Skillcard from "$lib/components/skillcard.svelte";
    import Projectcard from "$lib/components/projectcard.svelte";
    import "$lib/styles/containers.css";
    import "$lib/styles/text.css";

    // Images
    import UnityIcon from '$lib/assets/images/icons/unity.png';
    import BlenderIcon from '$lib/assets/images/icons/Blender_logo_no_text.svg';
    import FLIcon from '$lib/assets/images/icons/FL_Studio_11_just_logo.png';

    import AngularIcon from '$lib/assets/images/icons/Angular_full_color_logo.svg';
    import SvelteIcon from '$lib/assets/images/icons/Svelte_Logo.svg';
    import ReactIcon from '$lib/assets/images/icons/React-icon.svg';
    import NodeJSIcon from '$lib/assets/images/icons/nodejs-icon.svg';

    import SupabaseIcon from '$lib/assets/images/icons/supabase-icon.svg';
    import FirebaseIcon from '$lib/assets/images/icons/firebase.png';
    import MongoDBIcon from '$lib/assets/images/icons/mongodb.svg';
    import OracleIcon from '$lib/assets/images/icons/oracle.svg';


    import TrepidationCover from '$lib/assets/images/covers/trep.png';
    import TrepidationBG from '$lib/assets/images/backgrounds/TrepidationTitle.png';


    import UmusePlaylist from "$lib/assets/images/umuse/umuse2.png";
    import UmuseFullscreen from "$lib/assets/images/umuse/umuse8.png";

    import MH_BG from "$lib/assets/images/mhit/mh.jpg";



	import { onMount } from 'svelte';


    let gamedevIcons = [UnityIcon, BlenderIcon, FLIcon]
    let webdevIcons = [ReactIcon, SvelteIcon, AngularIcon, NodeJSIcon]
    let dbIcons = [SupabaseIcon, FirebaseIcon, MongoDBIcon, OracleIcon]

    onMount(() => {
        let elem = document.getElementById("bg-image") as HTMLElement;
        
        elem.style.backgroundImage = "";
        elem.classList.add("bg-fade-out");			
        elem.classList.remove("bg-fade-in");	
    })
</script>

<div>
    <h1>Welcome! Click "See More" to learn more about me.</h1>
    <button on:click={() => {goto("/about")}}>See more</button>
    
    
    <h2>Featured Projects</h2>
    <hr />
    <div class="card-section">
        <Projectcard id="trepidation-card" title="Trepidation" to="./projects/games/Trepidation" bg_img={TrepidationCover} cover_img={TrepidationBG} />
        <Projectcard id="mhit-card" title="Marshall Health IT Docs" to="./projects/personal/MHIT-Docs" bg_img={MH_BG} cover_img={MH_BG} />
        <Projectcard id="umuse-card" title="uMuse" to="./projects/personal/uMuse" bg_img={UmuseFullscreen} cover_img={UmusePlaylist} />
        <Projectcard id="wv-museum-card" to="./projects/academic/wv-state-museum" title="WV State Museum Project" />
    </div>
    
    <button on:click={()=> {goto("/projects")}}>View All</button>
    
    
    <h2>Skills</h2>
    <hr />
    <div class="card-section">
        <Skillcard title="Game Development" images={gamedevIcons} description="Highly skilled in developing games in Unity and composing music in FL Studio."/>
        <Skillcard title="Web Development" images={webdevIcons} description="Experienced in numerous JavaScript frameworks and NodeJS."/>
        <Skillcard title="Databases" images={dbIcons} description="Trained in various databases and SQL/NoSQL languages."/>
    </div>
</div>