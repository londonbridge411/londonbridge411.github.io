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

<div id={props.id} class="card" on:pointerenter={SetBackground} on:pointerleave={ClearBackground} on:click={OnClick}>
    <img src={props.cover_img} />
    <h2>{props.title}
        <hr />
</h2>
</div>

<style>
    .card
    {
        position: relative;
        display: flex;
        align-items: center;
        justify-content: center;
        text-align: center;
        user-select: none;
        text-wrap: wrap;
        color: white;

        background-color: gray;
        min-height: 200px;   
        min-width: 320px;

        height: 200px;   
        width: 320px;

        text-shadow: black 1px 5px 10px;
        -webkit-box-shadow: 0px 0px 33px -7px rgba(0,0,0,1);
        -moz-box-shadow: 0px 0px 33px -7px rgba(0,0,0,1);
        box-shadow: 0px 0px 33px -7px rgba(0,0,0,1);
        overflow: hidden;


        transition: all .25s ease-in-out;
    }

    img
    {
        height: 100%;
        filter: brightness(70%) !important;

        transition: all .25s ease-in-out;
    }



    .card:hover
    {

        height: 220px;
        min-width: 340px;
        width: 340px;

        -webkit-box-shadow: 0px 0px 33px -7px white;
        -moz-box-shadow: 0px 0px 33px -7px white;
        box-shadow: 0px 0px 33px -7px white;
    }

    .card:hover img
    {
        filter: brightness(100%) blur(5px) !important;
    }


    .card:active
    {
        transition: all .1s ease-in-out;
        min-height: 180px;   
        min-width: 280px;
        height: 180px;   
        width: 280px;
    }


    .card:active h2
    {
        filter: opacity(0%);
    }

    .card h2
    {
        padding-top: 35px;
        position: absolute;
        width: 320px;
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
        width: 70%;
        
    }
</style>