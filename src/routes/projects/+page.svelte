<script lang="ts">
	import Projectcard from "$lib/components/projectcard.svelte";
    import "$lib/styles/containers.css";

    import TrepidationCover from '$lib/assets/images/covers/trep.png';
    import TrepidationBG from '$lib/assets/images/backgrounds/TrepidationTitle.png';

    import RooMee from '$lib/assets/images/covers/RooMeeTitle.png';
    import Firewall from '$lib/assets/images/covers/Firewall.png';
    import Youtube from '$lib/assets/images/covers/YouTube2.png';
    import CS450 from '$lib/assets/images/covers/cs450.png';


</script>

<h1>Projects</h1>
<h2>Personal/Work</h2>
<hr />
<div class="card-section">
    <Projectcard title="MH IT Docs" bg_img={TrepidationCover} cover_img={TrepidationCover}/>
    <Projectcard id="umuse-card" title="uMuse" to="./projects/personal/uMuse" />


</div>

<h2>Video Games</h2>
<hr />
<div class="card-section">
    <Projectcard id="trepidation-card" title="Trepidation" to="./projects/games/Trepidation"  bg_img={TrepidationBG} cover_img={TrepidationCover} />
    <Projectcard id="firewall-card" title="Firewall" to="./projects/games/Firewall"  bg_img={Firewall} cover_img={Firewall} />
</div>
<h2>Academic</h2>
<hr />
<div class="card-section">
    <Projectcard title="WV State Museum Project" bg_img={TrepidationBG} cover_img={TrepidationCover} />
    <Projectcard title="RooMee" bg_img={RooMee} cover_img={RooMee} />
    <Projectcard title="You2be" bg_img={Youtube} cover_img={Youtube} />
    <Projectcard title="High_Bytes OS" bg_img={CS450} cover_img={CS450} />
    <Projectcard title="Minecraft Database" bg_img={TrepidationBG} cover_img={TrepidationCover} />
</div>