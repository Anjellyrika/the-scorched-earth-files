<script lang="ts">
	import CharlesWrightPortrait from '$lib/content (temporary)/photos (temporary)/chase-s3.jpg';
	import PortraitPlaceholder from '$lib/assets/portrait-placeholder.webp';
	import WipPage from '$lib/components/WIPPage.svelte';

	const sampleChars = [
		['Charles Wright', CharlesWrightPortrait, '/characters/charles_wright'],
		['Character A', PortraitPlaceholder, '/characters/'],
		['Character B', PortraitPlaceholder, '/characters/'],
	];
</script>

<h1>Characters</h1>
<div class="mt-10 flex gap-8">
	{#each sampleChars as [name, photo, href] (name)}
		<a {href} class="group transition odd:hover:rotate-4 even:hover:-rotate-4">
			<div class="bg-surface-300 inline-flex max-w-40 flex-col items-center p-2">
				<img src={photo} alt={name} class="max-h-36 w-full object-cover" />
				<div class="flex justify-center pt-2 text-center">
					<p
						class="font-heading text-surface-950 leading-tight font-medium group-hover:font-semibold"
					>
						{name}
					</p>
				</div>
			</div>
		</a>
	{/each}
</div>
<WipPage />
