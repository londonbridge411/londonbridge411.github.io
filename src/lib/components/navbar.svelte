<script lang="ts">
    import { goto } from "$app/navigation";


  function HandleScroll()
  {
    let nav:HTMLElement = window.document.getElementById("navbar") as HTMLElement;
    if (window.scrollY > 10) {
          nav.style.backgroundColor = "black";
          nav.style.boxShadow = "0px 0px 33px 11px rgba(0,0,0,1)";
      } else {
        nav.style.backgroundColor = "";
        nav.style.boxShadow = "";
      }
  }
</script>

<svelte:window on:scroll={HandleScroll} />

<nav id="navbar">
  <button on:click={() => goto("/")}>Home</button>
  <button on:click={() => goto("/about")}>About</button>
  <button on:click={() => goto("/projects")}>Projects</button>
  <button on:click={() => goto("./")}>Contact</button>
  <button >GitHub</button>
  <button on:click={() => window.location.assign("https://www.linkedin.com/in/london-bowen-70010a148/")}>LinkedIn</button>
  <button on:click={() => window.location.assign("https://drive.google.com/file/d/1JobAdz6G5RbFtd0nhQzbt1N_Zt2tM6KA/view?usp=sharing")}>Resume</button>
</nav>

  <style>
    nav
    {
        position: -webkit-sticky;
        position: sticky;
        top: 0;
        display: flex;
        gap: 10px;
        justify-content: flex-end;
        transition: all .5s ease-out;
        padding: 10px;
    }
  </style>