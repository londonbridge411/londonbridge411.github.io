<script lang="ts">
	import { goto } from "$app/navigation";
	import { onMount } from "svelte";

	let props = $props();
    
    function SetBackground()
    {
        let elem = window.document.getElementById("bg-image") as HTMLElement;
        elem.style.backgroundImage = "url(" + props.bg_img + ")";
        elem.classList.add("bg-fade-in");			
        elem.classList.remove("bg-fade-out");			
    }

    function ClearBackground()
    {
        let elem = window.document.getElementById("bg-image") as HTMLElement;
        //elem.style.transition = "all 1s ease-in-out";
        //background-image: linear-gradient(rgba(135, 122, 212, 0.5),rgba(34, 0, 73, 0.979)), url("/src/lib/assets/images/backgrounds/galaxy.jpg");

        elem.classList.add("bg-fade-out");			
        elem.classList.remove("bg-fade-in");			

        //elem.style.backgroundImage = "linear-gradient(rgba(135, 122, 212, 0.5),rgba(34, 0, 73, 0.979)), url('/src/lib/assets/images/backgrounds/galaxy.jpg')";
        //elem.style.backgroundImage = "linear-gradient(rgba(0, 0, 0, 1),rgba(0, 0, 0, 1)), url('/src/lib/assets/images/backgrounds/galaxy.jpg')";
    }

    function OnClick()
    {
        let elem = window.document.getElementById(props.id) as HTMLElement;
        elem.style.animation = "expand 1s forwards";
	
        goto(props.to);
    }

</script>

<div id={props.id} class="card" style="background-image:url({props.cover_img})" on:pointerenter={SetBackground} on:pointerleave={ClearBackground} on:click={OnClick}>
    <span><h2>{props.title}</h2><hr /></span>
</div>

<style>
    .card
    {
        min-height: 200px;   
        min-width: 300px;

        height: 200px;   
        width: 300px;

        background-color: rgb(53, 53, 53);
        background-repeat: no-repeat;
        background-size: cover;
        background-position: center;

        -webkit-box-shadow: 0px 0px 33px -7px rgba(0,0,0,1);
        -moz-box-shadow: 0px 0px 33px -7px rgba(0,0,0,1);
        box-shadow: 0px 0px 33px -7px rgba(0,0,0,1);

        display: flex;
        align-items: center;
        justify-content: center;
        user-select: none;
        transition: all .25s ease-in-out;
    }

    span
    {
        padding: 10px;
        width:100%;
        height:100%;
        justify-items: center;
        align-content: center;
        transition: all .25s ease-in-out;
        text-align: center;
    }


    .card:hover
    {

        height: 220px;
        min-width: 320px;
        width: 320px;

        -webkit-box-shadow: 0px 0px 33px -7px white;
        -moz-box-shadow: 0px 0px 33px -7px white;
        box-shadow: 0px 0px 33px -7px white;
    }


    .card:active
    {
        transition: all .1s ease-in-out;
        min-height: 180px;   
        min-width: 280px;
        height: 180px;   
        width: 280px;
    }

    .card:hover span
    {
        backdrop-filter: blur(5px);
    }

    .card h1
    {
        transition: all .25s ease-in-out;
    }

    .card hr
    {
        visibility: hidden;
        width:  0%;
        transition: all .35s ease-in-out;
        
    }

    .card:hover hr
    {        
        visibility: visible;
        width:  70%;
    }

</style>