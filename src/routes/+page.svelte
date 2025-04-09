<script>
	import './app.css';

	import Footer from '$lib/components/Footer.svelte';
</script>

<main class="flex h-screen flex-col items-center justify-around bg-gray-700">
	<div class="flex flex-col items-center gap-10 bg-amber-400">
		<h1>THE SCORCHED EARTH FILES</h1>
		<h2>The official wiki for the Scorched Earth TTRPG</h2>
		<nav class="bg-amber-500">
			<a href="/world">World</a>
			<a href="/characters">Characters</a>
			<a href="/places">Places</a>
			<a href="/items">Items</a>
		</nav>
	</div>
	<div class="bg-amber-300">
		<Footer />
	</div>
</main>
