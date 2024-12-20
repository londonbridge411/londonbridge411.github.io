<script>
	import Navbar from "$lib/components/navbar.svelte";
	import Skillcard from "$lib/components/skillcard.svelte";
    import Projectcard from "$lib/components/projectcard.svelte";

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


    let gamedevIcons = [UnityIcon, BlenderIcon, FLIcon]
    let webdevIcons = [ReactIcon, SvelteIcon, AngularIcon, NodeJSIcon]
    let dbIcons = [SupabaseIcon, FirebaseIcon, MongoDBIcon, OracleIcon]
</script>

<h1>Slider thing goes here or something cool goes here + Introduction. Covers whole screen</h1>
<button>See more</button>

<hr />

<h1>Featured Projects</h1>
<div class="skill-section">
    <Projectcard title="Trepidation" images={gamedevIcons} description="Highly skilled in developing games in Unity and composing music in FL Studio." bg_img={TrepidationCover} cover_img={TrepidationCover} />
    <Projectcard title="Marshall Health IT Docs" images={webdevIcons} description="Highly skilled in developing games in Unity and composing music in FL Studio."/>
    <Projectcard title="uMuse" images={dbIcons} description="Highly skilled in developing games in Unity and composing music in FL Studio."/>
    <Projectcard title="WV State Museum Project" images={dbIcons} description="Highly skilled in developing games in Unity and composing music in FL Studio."/>
</div>

<button>See more</button>

<hr />

<h1>Skills</h1>
<div class="skill-section">
    <Skillcard title="Game Development" images={gamedevIcons} description="Highly skilled in developing games in Unity and composing music in FL Studio."/>
    <Skillcard title="Web Development" images={webdevIcons} description="Highly skilled in developing games in Unity and composing music in FL Studio."/>
    <Skillcard title="Databases" images={dbIcons} description="Highly skilled in developing games in Unity and composing music in FL Studio."/>
</div>


<style>
    .skill-section
    {
        display: flex;
        gap: 20px;
    }
</style>
