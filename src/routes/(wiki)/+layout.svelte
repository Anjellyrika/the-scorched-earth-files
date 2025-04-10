<script lang="ts">
	import Footer from '$lib/components/Footer.svelte';

	let { children } = $props();
</script>

<div class="relative flex min-h-screen flex-col p-12">
	{@render children()}
	<div class="bg-surface-900 absolute inset-x-0 bottom-0 p-4">
		<Footer />
	</div>
</div>
