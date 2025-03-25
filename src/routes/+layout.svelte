<script lang="ts">
	import Toaster from '$lib/Toaster.svelte'
	import '../app.css';
	
	let { children } = $props();
</script>

<Toaster />

<div class="px-12 py-2 flex flex-col gap-2 items-center bg-orange-50 h-screen">
	<h1 class="h1 text-4xl text-amber-700">SpellOgic</h1>
	<div class="flex flex-row gap-2 border rounded-xs border-amber-700 border-3 p-2 w-full justify-center bg-white text-lg">
		<span>Home</span> |
		<span>Test1</span>
	</div>
	{@render children()}
</div>
