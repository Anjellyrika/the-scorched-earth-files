<script lang="ts">
	import Footer from '$lib/components/Footer.svelte';
	import SideNav from '$lib/components/SideNav.svelte';

	let { children } = $props();
</script>

<div class="flex flex-col min-h-screen">
	<div class="fixed bottom-0 self-center md:self-auto md:top-28 h-fit min-w-16 z-10">
		<SideNav />
	</div>
	<main class="flex grow flex-col p-12 md:px-20">
		{@render children()}
	</main>
	<div class="bg-surface-900 w-full p-4 md:pb-4 pb-16">
		<Footer />
	</div>
</div>
