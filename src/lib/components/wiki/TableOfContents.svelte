<script lang="ts">
	const { contents, hasGallery } = $props();
</script>

<div class="bg-surface-600 w-fit space-y-2">
	<h3 class="border-surface-400 border-b-1 p-4 text-center">Contents</h3>
	<ol class="grid gap-2 p-4">
		{#each Object.keys(contents) as heading (heading)}
			<li>
				<a href="#{heading}" class="text-surface-50 font-heading hover:underline">
					&gt;&gt; {heading}</a
				>
			</li>
		{/each}
		{#if hasGallery}
			<li>
				<a href="#gallery" class="text-surface-50 font-heading hover:underline">
					&gt;&gt; gallery</a
				>
			</li>
		{/if}
	</ol>
</div>
