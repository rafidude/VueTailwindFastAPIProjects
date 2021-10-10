<script>
	import { Router, Link, Route } from "svelte-routing";
	import Welcome from "./pages/Welcome.svelte";
	import GameHub from "./pages/GameHub.svelte";

	let name = 'Test';
	export let url = "";
</script>

<main>
	<Router url="{url}">
	<!-- <nav>
		<Link to="/">Welcome</Link>
		<Link to="game-hub">Gamehub</Link>
	</nav> -->
	<div>
		<Route path="game-hub" component="{GameHub}" />
		<Route path="/"><Welcome /></Route>
	</div>
	</Router>

</main>