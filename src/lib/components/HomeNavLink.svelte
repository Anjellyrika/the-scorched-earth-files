<script lang="ts">
	import Icon from '@iconify/svelte';

	let { path, text, icon } = $props();
</script>

<a
	class="group bg-primary-500 relative inline-flex items-center gap-2 px-3 py-1 shadow-xl transition hover:shadow-2xl"
	href={path}
	title={text}
>
	<span
		class="group-hover:bg-primary-700 absolute inset-y-0 left-0 w-1 transition-all duration-300 group-hover:w-full"
	></span>
	<Icon class="relative" {icon} width={20} color="#f8f8f8" />
	<span class="text-surface-50 relative font-normal">{text}</span>
</a>
