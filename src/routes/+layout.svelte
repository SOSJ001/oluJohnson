<script lang="ts">
	import Header from '$lib/components/Header.svelte';

	
	import '../app.css';
	// Supports weights 100-900
	import '@fontsource-variable/roboto-slab';
	let { children } = $props();
</script>
<!-- Navigation Bar -->
<Header />
{@render children()}
