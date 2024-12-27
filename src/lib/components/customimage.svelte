<script lang="ts">
    let props = $props();
    
    
    function GetHeight()
    {
            return props.height ? props.height + "px" : "auto";
    }

    function GetWidth()
    {
            return props.width ? props.width + "px" : "auto";
    }
</script>



<a href={props.src} style="height: {GetHeight()}; width: {GetWidth()};">
    <img src={props.src} style="height: {GetHeight()}; width: {GetWidth()};" />
    <h3>{props.text}</h3>
</a>


<style>
    a
    {
        position: relative;
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
        width: 95% !important;
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