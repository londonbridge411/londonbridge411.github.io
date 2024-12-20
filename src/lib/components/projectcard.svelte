<script lang="ts">
	import { onMount } from "svelte";

	let props = $props();
    

    onMount(() => {
        
    });
</script>

<div class="card" style="background-image:url({props.cover_img})">
    <span><h1>{props.title}</h1><hr /></span>
</div>

<style>
    .card
    {
        height: 200px;   
        width: 300px;
        background-color: rgb(53, 53, 53);
        background-repeat: no-repeat;
        background-size: cover;

        -webkit-box-shadow: 0px 0px 33px -7px rgba(0,0,0,1);
        -moz-box-shadow: 0px 0px 33px -7px rgba(0,0,0,1);
        box-shadow: 0px 0px 33px -7px rgba(0,0,0,1);

        display: flex;
        align-items: center;
        justify-content: center;
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
    }


    .card:hover
    {
        -webkit-box-shadow: 0px 0px 33px -7px rgb(255, 255, 255);
        -moz-box-shadow: 0px 0px 33px -7px rgb(255, 255, 255);
        box-shadow: 0px 0px 33px -7px rgb(255, 255, 255);
    }

    .card:hover span
    {
        backdrop-filter: blur(5px);
    }

    .card h1
    {
        transition: all .25s ease-in-out;
    }

    .card:hover h1
    {
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