<script>
	import Footer from '$lib/components/Footer.svelte';
	import Hero from '$lib/components/Hero.svelte';
	import Services from '$lib/components/services.svelte';
	import TrustedCompanies from '$lib/components/TrustedCompanies.svelte';
	import WhyChooseUs from '$lib/components/whyChooseUs.svelte';
</script>

<div class="bg-gray-100 font-sans leading-normal tracking-normal">
	<!-- Hero Section -->
	<Hero />

	<!-- Services Section -->
	<Services />

	<!-- Trusted By Section -->
	<TrustedCompanies />

	<!-- why choose us -->
	<WhyChooseUs />

	<!-- Footer -->
	<Footer />
</div>

<style>
	div {
		font-family: 'Roboto Slab Variable', serif;
	}
</style>
