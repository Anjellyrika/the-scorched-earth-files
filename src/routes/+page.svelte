<script>
	import './app.css';

	import Character from '@iconify-icons/game-icons/character';
	import Cube from '@iconify-icons/game-icons/cube';
	import DetectiveTable from '$lib/assets/detective-table.webp';
	import Footer from '$lib/components/Footer.svelte';
	import HomeNavLink from '$lib/components/HomeNavLink.svelte';
	import PositionMarker from '@iconify-icons/game-icons/position-marker';
	import World from '@iconify-icons/game-icons/world';
</script>

<div
	class="bg-surface-950 relative flex h-screen flex-col justify-center bg-cover bg-position-[0%_60%] px-12 bg-blend-multiply brightness-90"
	style="background-image: url({DetectiveTable})"
>
	<main class="flex flex-col items-center gap-12 text-center max-[400px]:gap-4">
		<div class="space-y-8">
			<h1 class="font-title text-surface-100 text-shadow-lg md:text-6xl">
				THE SCORCHED EARTH FILES
			</h1>
			<h5 class="text-surface-200 text-shadow-lg">
				The official wiki for the Scorched Earth TTRPG
			</h5>
		</div>
		<nav class="flex flex-col gap-3 md:flex-row">
			<HomeNavLink path="/world" text="World" icon={World} />
			<HomeNavLink path="/characters" text="Characters" icon={Character} />
			<HomeNavLink path="/places" text="Places" icon={PositionMarker} />
			<HomeNavLink path="/items" text="Items" icon={Cube} />
		</nav>
	</main>
	<footer
		class="text-surface-300 absolute inset-x-0 bottom-0 px-8 text-center text-xs md:py-2 md:text-base"
	>
		<Footer />
	</footer>
</div>
