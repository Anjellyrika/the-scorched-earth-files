<script lang="ts">
	import Icon, { type IconifyIcon } from '@iconify/svelte';

	import { base } from '$app/paths';

	import Character from '@iconify-icons/game-icons/character';
	import Cube from '@iconify-icons/game-icons/cube';
	import House from '@iconify-icons/game-icons/house';
	import PositionMarker from '@iconify-icons/game-icons/position-marker';
	import World from '@iconify-icons/game-icons/world';
</script>

{#snippet Tab(path: string, label: string, icon: IconifyIcon, bgColorClass: string)}
	<a
		href={base}{path}
		aria-label={label}
		class={`${bgColorClass} text-surface-50 w-fit rounded-t-2xl md:rounded-t-none md:rounded-r-2xl p-4 transition-all hover:pl-6`}
	>
		<Icon {icon} width={20} />
	</a>
{/snippet}

<div class="grid grid-flow-col md:grid-flow-row">
	{@render Tab('/', 'Home', House, 'bg-primary-500')}
	{@render Tab('/world', 'World', World, 'bg-secondary-500')}
	{@render Tab('/characters', 'Characters', Character, 'bg-tertiary-500')}
	{@render Tab('/places', 'Places', PositionMarker, 'bg-primary-600')}
	{@render Tab('/items', 'Items', Cube, 'bg-secondary-700')}
</div>
