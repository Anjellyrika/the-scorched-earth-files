<script>
	import { base } from '$app/paths';
	import { onNavigate } from '$app/navigation';

	import Character from '@iconify-icons/game-icons/character';
	import Cube from '@iconify-icons/game-icons/cube';
	import DetectiveTable from '$lib/assets/detective-table.webp';
	import Footer from '$lib/components/Footer.svelte';
	import HomeNavLink from '$lib/components/HomeNavLink.svelte';
	import PositionMarker from '@iconify-icons/game-icons/position-marker';
	import World from '@iconify-icons/game-icons/world';

	onNavigate((navigation) => {
		if (!document.startViewTransition) return;

		return new Promise((resolve) => {
			document.startViewTransition(async () => {
				resolve();
				await navigation.complete;
			});
		});
	});
</script>

<div
	class="bg-surface-950 relative flex h-screen flex-col justify-center bg-cover bg-position-[0%_60%] px-12 bg-blend-multiply brightness-90"
	style="background-image: url({DetectiveTable})"
>
	<main class="flex flex-col items-center gap-12 text-center max-[400px]:gap-4">
		<div class="space-y-8">
			<h1
				class="font-title text-surface-100 motion-safe:animate-float-in text-shadow-lg md:text-6xl"
			>
				THE SCORCHED EARTH FILES
			</h1>
			<h5
				class="text-surface-200 text-sm text-shadow-lg motion-safe:animate-[float-in_0.5s] md:text-xl"
			>
				The official wiki for the Scorched Earth TTRPG
			</h5>
		</div>
		<nav class="flex flex-col gap-3 motion-safe:animate-[float-in_0.58s] md:flex-row">
			<HomeNavLink path="{base}/world" text="World" icon={World} />
			<HomeNavLink path="{base}/characters" text="Characters" icon={Character} />
			<HomeNavLink path="{base}/places" text="Places" icon={PositionMarker} />
			<HomeNavLink path="{base}/items" text="Items" icon={Cube} />
		</nav>
	</main>
	<footer
		class="text-surface-300 absolute inset-x-0 bottom-0 px-4 text-center text-xs md:py-2 md:text-base"
	>
		<Footer />
	</footer>
</div>
