<script>
	import Footer from '$lib/components/Footer.svelte';

	// No JavaScript logic needed for static page

	import Header from '$lib/components/Header.svelte';
	import Hero from '$lib/components/Hero.svelte';
	import Services from '$lib/components/services.svelte';
	import TrustedCompanies from '$lib/components/TrustedCompanies.svelte';
</script>

<div class="bg-gray-100 font-sans leading-normal tracking-normal">
	<!-- Navigation Bar -->
	<Header />

	<!-- Hero Section -->
	<Hero />

	<!-- Services Section -->
	<Services />

	<!-- Trusted By Section -->
	<TrustedCompanies/>

	<!-- Footer -->
	<Footer/>
</div>

<style>
	div {
		font-family: 'Roboto Slab Variable', serif;
	}
</style>
