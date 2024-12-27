<script lang="ts">
    import clickOutside from "$lib/clickOutside";
    import "$lib/styles/text.css";
    import "$lib/styles/project-page.css"
    
    import Youtube from '$lib/assets/images/covers/YouTube2.png';
	import { onDestroy, onMount } from "svelte";

    onMount(() => {
        let elem = document.getElementById("bg-image") as HTMLElement;
        
        elem.style.backgroundImage = "url(" + Youtube + ")";
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

<h1 class="title">You2be</h1>
<div class="blur" />

<div use:clickOutside on:click_outside={GoBack} id="test" class="project-page-container">
    <div class="main-image" >
        <img src={Youtube} />
        <p class="context">Image of home page</p>
    </div>

    <hr />
    

    <h2 class="subtitle">Description</h2>
    <p class="regular-text">
        This was a project I did for my Software Engineering lab. We each had a different website.
        The goal was for us to learn HTML, CSS, Bootstrap, Angular, and Firebase. Due to the massive 
        scope our lab TA had in the beginning, he ended up lessening the workload a little bit and 
        had us do specific parts. For instance, the video cards are linked to Firebase's realtime 
        database which holds all of the data regarding the thumbnail.
    </p>

    <h2 class="subtitle">Contributions</h2>
    <h2 class="subtitle">Media</h2>
</div>
