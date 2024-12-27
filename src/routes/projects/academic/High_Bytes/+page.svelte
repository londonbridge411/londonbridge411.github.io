<script lang="ts">
    import clickOutside from "$lib/clickOutside";
    import "$lib/styles/text.css";
    import "$lib/styles/project-page.css"
    
    import CS450 from '$lib/assets/images/covers/cs450.png';
	import { onDestroy, onMount } from "svelte";

    onMount(() => {
        let elem = document.getElementById("bg-image") as HTMLElement;
        
        elem.style.backgroundImage = "url(" + CS450 + ")";
        elem.classList.add("bg-fade-in");			
        elem.classList.remove("bg-fade-out");	
    })

    onDestroy(() => {
        //elem = document.getElementById("bg-image") as HTMLElement;
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

<h1 class="title">High_Bytes OS</h1>
<div class="blur" />

<div use:clickOutside on:click_outside={GoBack} id="test" class="project-page-container">
    <div class="main-image" >
        <img src={CS450} />
        <p class="context">Image of some code.</p>
    </div>

    <hr />
    

    <h2 class="subtitle">Description</h2>
    <p class="regular-text">
        High_Bytes OS is a command based OS built off C and ASM. Features included: polling, multi-processing, process control 
        block management, and heap management. Towards the end, we attempted to make the OS interrupt-based rather than polled.
        Due to time constraints and finals, we were unable to get it fully working.
    </p>
    <p class="regular-text">
        I currently do not have a way to access the repo as it is locked down by the teacher.
    </p>

    <h2 class="subtitle">Contributions</h2>
    <ul>
        <li>Developed the Heap Manager</li>
        <li>Created many of the process control block (PCB) functions that dealt with memory</li>
        <li>Created the PCB queue and functions surrounding it</li>
        <li>Implemented string functions for extra credit</li>
        <li>Create alarm PCB fuctionality</li>
        <li>Aided in making the OS interrupt-based</li>
    </ul>
    <h2 class="subtitle">Media</h2>
    <h2>Links</h2>
    <a href="https://docs.google.com/document/d/1dB9rY0IsjZqT_DZ-KnonkQrJiXsbAb_BwkKNKLlwGkw/edit?usp=sharing">Programmers Manual</a>
</div>
