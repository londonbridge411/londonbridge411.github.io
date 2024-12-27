<script lang="ts">
	import Projectcard from "$lib/components/projectcard.svelte";
    import "$lib/styles/containers.css";
    import "$lib/styles/text.css";


    import TrepidationCover from '$lib/assets/images/covers/trep.png';
    import TrepidationBG from '$lib/assets/images/backgrounds/TrepidationTitle.png';

    import UmusePlaylist from "$lib/assets/images/umuse/umuse2.png";
    import UmuseFullscreen from "$lib/assets/images/umuse/umuse8.png";

    import MH_BG from "$lib/assets/images/mhit/mh.jpg";

    import RooMee from '$lib/assets/images/covers/RooMeeTitle.png';
    import Firewall from '$lib/assets/images/covers/Firewall.png';
    import Youtube from '$lib/assets/images/covers/YouTube2.png';
    import CS450 from '$lib/assets/images/covers/cs450.png';
	import { onMount } from "svelte";

    onMount(() => {
        let elem = document.getElementById("bg-image") as HTMLElement;
        
        elem.style.backgroundImage = "";
        elem.classList.add("bg-fade-out");			
        elem.classList.remove("bg-fade-in");	
    })

</script>

<h1>Projects</h1>
<h2>Personal/Work</h2>
<hr />
<div class="card-section">
    <Projectcard id="mhit-card" title="Marshall Health IT Docs" to="./projects/personal/MHIT-Docs" bg_img={MH_BG} cover_img={MH_BG}/>
    <Projectcard id="umuse-card" title="uMuse" to="./projects/personal/uMuse" bg_img={UmuseFullscreen} cover_img={UmusePlaylist} />
</div>

<h2>Video Games</h2>
<hr />
<div class="card-section">
    <Projectcard id="trepidation-card" title="Trepidation" to="./projects/games/Trepidation"  bg_img={TrepidationCover} cover_img={TrepidationBG} />
    <Projectcard id="firewall-card" title="Firewall" to="./projects/games/Firewall"  bg_img={Firewall} cover_img={Firewall} />
</div>
<h2>Academic</h2>
<hr />
<div class="card-section">
    <Projectcard id="wv-museum-card" to="./projects/academic/wv-state-museum" title="WV State Museum Project" />
    <Projectcard id="roomee-card" to="./projects/academic/RooMee" title="RooMee" bg_img={RooMee} cover_img={RooMee} />
    <Projectcard id="you2be-card" to="./projects/academic/You2be" title="You2be" bg_img={Youtube} cover_img={Youtube} />
    <Projectcard id="hb-card" to="./projects/academic/High_Bytes" title="High_Bytes OS" bg_img={CS450} cover_img={CS450} />
    <Projectcard id="mcdb-card" to="./projects/academic/MCDB" title="Minecraft Database" bg_img={TrepidationBG} cover_img={TrepidationCover} />
</div>