<script lang="ts">
    import { goto } from "$app/navigation";
    import Github from "$lib/assets/images/icons/github.svg";
    import LinkedIn from "$lib/assets/images/icons/linkedin.svg";

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
  <button on:click={() => goto("/projects")}>Projects</button>
  <button on:click={() => goto("/about")}>About</button>
  <button on:click={() => window.location.assign("src/lib/assets/Software Dev Resume.pdf")}>Résumé</button>
  <img class="img-button" src={Github} on:click={() => window.location.assign("https://github.com/londonbridge411")} />
  <img class="img-button" src={LinkedIn} on:click={() => window.location.assign("https://www.linkedin.com/in/london-bowen-70010a148/")} />
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

    .img-button
    {
      width: 25px;
			background: transparent;
			border-color: transparent;		
			border-width: 1px;
			font-family: "Roboto", serif;	
			border-style: solid;
			font-size: large;
			user-select: none;
			transition: all .25s ease-in-out;
      padding: 10px;
    }

		.img-button:hover
		{
			border-color: white;
		}

  </style>