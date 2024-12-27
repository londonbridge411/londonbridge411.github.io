<script lang="ts">
    let props = $props();
</script>

<a href={props.src}>
    <img src={props.src}/>
    <h3>{props.text}</h3>
</a>


<style>


    a
    {
        width: 350px;
        display: flex;
        align-items: center;
        justify-content: center;
        text-align: center;
        user-select: none;
        text-wrap: wrap;
        color: white;
    }

    h3
    {
        position: absolute;
        opacity: 0;
        width: 300px;
    }

    img
    {
        width: 350px;
    }

    a, img, h3
    {
        transition: all 0.5s ease-in-out;
    }

    a:hover img
    {
        filter: brightness(50%);
    }

    a:hover h3
    {
        opacity: 100;
    }


</style>