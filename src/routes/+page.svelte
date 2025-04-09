<script>
	import './app.css';

	import Footer from '$lib/components/Footer.svelte';
</script>

<main class="flex h-screen flex-col items-center justify-around">
	<div class="flex flex-col items-center gap-10">
		<h1 class="font-title text-6xl">THE SCORCHED EARTH FILES</h1>
		<h2>The official wiki for the Scorched Earth TTRPG</h2>
		<nav>
			<a href="/world">World</a>
			<a href="/characters">Characters</a>
			<a href="/places">Places</a>
			<a href="/items">Items</a>
		</nav>
	</div>
	<div>
		<Footer />
	</div>
</main>
