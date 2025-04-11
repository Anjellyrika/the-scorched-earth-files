<script lang="ts">
	// Define infos here temporarily
	import CharacterQuote from '$lib/components/wiki/CharacterQuote.svelte';
	import CharlesPortrait from '$lib/content (temporary)/photos (temporary)/chase-s3.jpg';
	import ChaseHS from '$lib/content (temporary)/photos (temporary)/chase-hs.jpg';
	import ChasePage from '$lib/content (temporary)/Chase.json';
	import ChaseS1 from '$lib/content (temporary)/photos (temporary)/chase-s1.png';
	import ChaseS2 from '$lib/content (temporary)/photos (temporary)/Scar.png';
	import Infobox from '$lib/components/wiki/InfoboxCharacter.svelte';
	import TableOfContents from '$lib/components/wiki/TableOfContents.svelte';

	let portrait = CharlesPortrait;
	let gallery = [ChaseHS, ChaseS1, ChaseS2, CharlesPortrait];

	const displayName = ChasePage.displayname;
	const bio = ChasePage.bio;
	const role = ChasePage.role;
	const main = ChasePage.mainContent;
</script>

<main>
	<section class="flex flex-col gap-4 md:flex-row-reverse md:gap-12">
		<h1 class="text-center text-3xl md:hidden">{displayName}</h1>
		<Infobox image={portrait} {bio} {role} />
		<section class="space-y-4">
			<h1 class="hidden whitespace-nowrap md:block">{displayName}</h1>
			<CharacterQuote>{ChasePage.characterQuote}</CharacterQuote>
			<p class="text-surface-300 leading-relaxed">{ChasePage.shortIntro}</p>
			<TableOfContents contents={main} hasGallery={true} />
		</section>
	</section>
	<section>
		{#each Object.entries(main) as [heading, content] (heading)}
			<div class="my-12">
				<h2 id={heading} class="border-surface-300 mb-2 w-fit border-b-1">
					{heading.toUpperCase()}
				</h2>
				{#if heading === 'introduction'}
					<p class="text-surface-300 leading-relaxed">{content}</p>
				{:else if heading === 'trivia' && Array.isArray(content)}
					<ul class="list-inside list-disc">
						{#each content as trivia (trivia)}
							<li class="text-surface-300">{trivia}</li>
						{/each}
					</ul>
				{:else}
					{#each Object.entries(content) as [subheading, innerContent] (subheading)}
						<div class="my-8">
							<h3 class="text-surface-200 border-surface-600 mb-2 w-fit border-b-1">
								{subheading.toUpperCase()}
							</h3>
							<p class="text-surface-300 leading-relaxed">{innerContent}</p>
						</div>
					{/each}
				{/if}
			</div>
		{/each}
	</section>
	<section>
		<h2 id="gallery" class="border-surface-300 mb-2 w-fit border-b-1">GALLERY</h2>
		<div class="grid grid-flow-row gap-4 md:grid-cols-4">
			{#each gallery as photo (photo)}
				<div class="odd:hover:rotate-2 even:hover:-rotate-2">
					<img
						src={photo}
						alt=""
						class="hover:border-surface-300 hover:bg-surface-300 h-69 w-full object-cover object-top transition-transform hover:scale-105 hover:border-9 hover:pb-8 hover:shadow-xl"
					/>
				</div>
			{/each}
		</div>
	</section>
</main>
