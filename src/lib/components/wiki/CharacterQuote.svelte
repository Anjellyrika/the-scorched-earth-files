<script lang="ts">
	const { children } = $props();
</script>

<div class="bg-secondary-500 m-8 flex gap-6 p-6 shadow-xl">
	<h1 class="font-title text-5xl italic">"</h1>
	{@render children()}
</div>
