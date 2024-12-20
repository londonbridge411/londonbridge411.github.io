<script lang="ts">
	let props = $props();
</script>

<div class="card">

    <div class="icons">
        {#each props.images as imageURL}
            <img src={imageURL} />
        {/each}
    </div>
    <hr />

    <h1>{props.title}</h1>
    <p>{props.description}</p>
</div>

<style>
    .card
    {
        height: 200px;   
        width: 300px;
        background-color: rgb(53, 53, 53);
        
        -webkit-box-shadow: 0px 0px 33px -7px rgba(0,0,0,1);
        -moz-box-shadow: 0px 0px 33px -7px rgba(0,0,0,1);
        box-shadow: 0px 0px 33px -7px rgba(0,0,0,1);

        padding: 10px;
    }

    .icons
    {
        display: flex;
        gap: 10px;
    }

    .icons img
    {
        height: 32px;   
    }

    h1
    {
        margin-top: 0;
    }
</style>