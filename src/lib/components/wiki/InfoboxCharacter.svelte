<script lang="ts">
	const { image, bio, role } = $props();
</script>

<aside class="min-w-75 place-self-center md:place-self-end">
	<img src={image} alt={bio.fullname} />
	<div class="bg-surface-800 text-center"><h4>BIO</h4></div>
	<div class="grid grid-cols-2">
		{#each Object.entries(bio) as [field, info] (field)}
			<div class="bg-surface-900 border-surface-600 border-b-1 px-2">
				<h6>{field.toUpperCase()}</h6>
			</div>
			<div class="bg-surface-700 border-surface-500 border-b-1 px-2 py-1 text-sm">
				{#if Array.isArray(info)}
					<p>{info.join(', ')}</p>
				{:else}
					<p>{info}</p>
				{/if}
			</div>
		{/each}
	</div>
	<div class="bg-surface-800 text-center"><h4>ROLE</h4></div>
	<div class="grid grid-cols-2">
		{#each Object.entries(role) as [field, info] (field)}
			<div class="bg-surface-900 border-surface-600 border-b-1 px-2">
				<h6>{field.toUpperCase()}</h6>
			</div>
			<div class="bg-surface-700 border-surface-500 border-b-1 px-2 py-1 text-sm">
				{#if Array.isArray(info)}
					<p>{info.join(', ')}</p>
				{:else}
					<p>{info}</p>
				{/if}
			</div>
		{/each}
	</div>
</aside>
