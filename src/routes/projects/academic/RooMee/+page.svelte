<script lang="ts">
    import clickOutside from "$lib/clickOutside";

    import RooMee from '$lib/assets/images/covers/RooMeeTitle.png';
	import { onDestroy, onMount } from "svelte";

    onMount(() => {
        let elem = document.getElementById("bg-image") as HTMLElement;
        
        elem.style.backgroundImage = "url(" + RooMee + ")";
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

<h1 class="title">RooMee</h1>
<div class="blur" />

<div use:clickOutside on:click_outside={GoBack} id="test" class="project-page-container">
    <div class="main-image" >
        <img src={RooMee} />
        <p class="context">Image of the login screen</p>
    </div>

    <hr />
    

    <h2 class="subtitle">Description</h2>
    <p class="regular-text">
        RooMee was our final project for our Software Engineering class.
        The idea of it is that users can set preferences and info about what
         they are looking for in terms of price and roommate personality. 
         The app functions similar to Tinder in that it's a swipe app. The 
         challenge was that we only had about 2.5 months to fully create it. 
         I believe only 2 or 3 groups out of 12 finished their project. We ran 
         into issues when designing the database due to our lack of knowledge. 
         This ate up most of our time but once we got it working, we starting
          making a lot more progress. The issue was it was too late.
    </p>
    <h2 class="subtitle">Contributions</h2>
    <ul>
        <li>Led a team of 5 other students.</li>
        <li>Worked as the lead programmer.</li>
        <li>Implemented connection with Firebase.</li>
        <li>Programmed the REST API with Firebase</li>
        <li>Implemented User Authentication.</li>
        <li>Designed and created the login/signup screen.</li>
    </ul>
    <h2 class="subtitle">Media</h2>
</div>
