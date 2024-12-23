<script>
	import { fade } from 'svelte/transition';
    import { goto } from "$app/navigation";
	import Navbar from "$lib/components/navbar.svelte";
	import Skillcard from "$lib/components/skillcard.svelte";
    import Projectcard from "$lib/components/projectcard.svelte";
    import "$lib/styles/containers.css";

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


    let gamedevIcons = [UnityIcon, BlenderIcon, FLIcon]
    let webdevIcons = [ReactIcon, SvelteIcon, AngularIcon, NodeJSIcon]
    let dbIcons = [SupabaseIcon, FirebaseIcon, MongoDBIcon, OracleIcon]
</script>

<div>
    <h1>Slider thing goes here or something cool goes here + Introduction. Covers whole screen</h1>
    <button>See more</button>
    
    <hr />
    
    <h1>Featured Projects</h1>
    <div class="card-section">
        <Projectcard id="trepidation-card" title="Trepidation" to="./projects/games/Trepidation" bg_img={TrepidationBG} cover_img={TrepidationCover} />
        <Projectcard title="MH IT Docs" bg_img={TrepidationCover} cover_img={TrepidationCover}/>
        <Projectcard id="umuse-card" title="uMuse" />
        <Projectcard title="WV State Museum Project" />
    </div>
    
    <button on:click={()=> {goto("/projects")}}>See more</button>
    
    <hr />
    
    <h1>Skills</h1>
    <div class="card-section">
        <Skillcard title="Game Development" images={gamedevIcons} description="Highly skilled in developing games in Unity and composing music in FL Studio."/>
        <Skillcard title="Web Development" images={webdevIcons} description="Experienced in numerous JavaScript frameworks and NodeJS."/>
        <Skillcard title="Databases" images={dbIcons} description="Trained in various databases and SQL/NoSQL languages."/>
    </div>
</div>