<script>
	import BreadCrumb from '$lib/components/BreadCrumb.svelte';
	import Footer from '$lib/components/Footer.svelte';
	import Bank from '$lib/components/Industries/Bank.svelte';
	import Offices from '$lib/components/Industries/Offices.svelte';
	import Institutions from '$lib/components/Institutions.svelte';
</script>

<!-- Main Content -->
<BreadCrumb />
<main class="container mx-auto px-4">
	<!-- Hero Section -->
	<section
		style="background-image: url('/purple-Bg.jpg');"
		class="relative mb-5 rounded-lg bg-gray-800 bg-cover bg-no-repeat px-3 py-6 text-gray-200 md:px-10 md:py-20"
	>
		<div class="animate-fade-in">
			<h1 class="mb-6 text-4xl font-bold md:text-5xl">Industries Served</h1>
			<p class="text-lg">
				Tailored hardware repair and software solutions for key sectors across West Africa and
				beyond.
			</p>
			<p class="text-lg">Discover how we add value to your industry.</p>
		</div>
	</section>

	<!-- Industry Tabs -->
	<nav class="mb-10 overflow-auto p-2 shadow">
		<ul class="flex space-x-4">
			<li>
				<a
					href="#banks"
					class="order-purple-600 border-b-2 border-purple-600 pb-1 text-lg font-medium">Banks</a
				>
			</li>
			<li>
				<a
					href="#offices"
					class="border-b-2 border-transparent pb-1 text-lg font-medium hover:border-purple-600"
					>Offices</a
				>
			</li>
			<li>
				<a
					href="#institutions"
					class="border-b-2 border-transparent pb-1 text-lg font-medium hover:border-purple-600"
					>Institutions</a
				>
			</li>
		</ul>
	</nav>

	<!-- Banks Section -->
	<Bank />

	<!-- Offices Section -->
	<Offices />

	<!-- Institution Section -->
	<Institutions />

	<!-- Call-to-Action -->
	<section class="mb-10">
		<h3 class="mb-6 text-xl font-bold">Need a custom solution for your sector?</h3>
		<a
			href="/Contact"
			class="rounded bg-purple-600 px-6 py-3 font-bold text-white transition hover:bg-purple-700"
			>Contact Our Team</a
		>
	</section>
</main>
<Footer />

<style>
	@keyframes fadeIn {
		from {
			opacity: 0;
			transform: translateY(20px);
		}
		to {
			opacity: 1;
			transform: translateY(0);
		}
	}

	.animate-fade-in {
		animation: fadeIn 1s ease-out forwards;
	}
</style>
