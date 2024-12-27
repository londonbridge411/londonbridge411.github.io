<script>
	import { onNavigate } from "$app/navigation";
	import Navbar from "$lib/components/navbar.svelte";
    import "$lib/index";

	// Please ignore the startViewTransition error. This will not work in FireFox!
	onNavigate(() => {
		if (!document.startViewTransition) return;

		return new Promise((fufill) => 
			document.startViewTransition(() => new Promise(fufill))
		)
	})
</script>
<Navbar />
<main><slot /></main>