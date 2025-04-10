<script lang="ts">
	import Footer from '$lib/components/Footer.svelte';
	import SideNav from '$lib/components/SideNav.svelte';

	let { children } = $props();
</script>

<div class="relative flex min-h-screen">
	<div class="sticky top-24 h-full min-w-16">
		<SideNav />
	</div>
	<main class="flex grow flex-col p-12">
		{@render children()}
	</main>
</div>
<div class="bg-surface-900 w-full p-4">
	<Footer />
</div>
