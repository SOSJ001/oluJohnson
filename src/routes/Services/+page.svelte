<script>
	// @ts-ignore
	import BreadCrumb from '$lib/components/BreadCrumb.svelte';
	import Footer from '$lib/components/Footer.svelte';
	import {
		CreditCardIcon,
		HeadphonesIcon,
		LinkIcon,
		PhoneIncomingIcon,
		PrinterIcon,
		ShieldIcon,
		ThumbsUpIcon,
		TruckIcon
	} from 'svelte-feather-icons';

	// SEO Meta Tags for Services page
	import { page } from '$app/stores';

	// Set page-specific meta tags
	$: page.title = 'IT Services & Hardware Repair - Olu Johnson Business Technical Services';
	$: page.meta = {
		description:
			'Professional IT services including printer repair, computer maintenance, cheque encoder service, and custom software development. Serving banks, offices, and institutions across West Africa.',
		keywords:
			'IT services, hardware repair, printer repair, computer repair, cheque encoder service, custom software development, West Africa, Nigeria, Lagos, banking IT support, office equipment repair',
		canonical: 'https://www.olujohnsonbusinesstechnicalservices.com/Services'
	};
</script>

<!-- Page-specific SEO Meta Tags -->
<svelte:head>
	<!-- Enhanced SEO for Services page -->
	<meta
		name="description"
		content="Professional IT services including printer repair, computer maintenance, cheque encoder service, and custom software development. Serving banks, offices, and institutions across West Africa."
	/>
	<meta
		name="keywords"
		content="IT services, hardware repair, printer repair, computer repair, cheque encoder service, custom software development, West Africa, Nigeria, Lagos, banking IT support, office equipment repair, on-site support, network setup"
	/>

	<!-- Open Graph for Services -->
	<meta
		property="og:title"
		content="IT Services & Hardware Repair - Professional Technical Support"
	/>
	<meta
		property="og:description"
		content="Comprehensive hardware repair and custom software solutions for banks, offices, and institutions. Expert IT services across West Africa."
	/>
	<meta property="og:type" content="website" />
	<meta
		property="og:image"
		content="https://www.olujohnsonbusinesstechnicalservices.com/4111232.png"
	/>
	<meta property="og:url" content="https://www.olujohnsonbusinesstechnicalservices.com/Services" />

	<!-- Twitter Card for Services -->
	<meta name="twitter:card" content="summary_large_image" />
	<meta
		name="twitter:title"
		content="IT Services & Hardware Repair - Professional Technical Support"
	/>
	<meta
		name="twitter:description"
		content="Comprehensive hardware repair and custom software solutions for banks, offices, and institutions. Expert IT services across West Africa."
	/>
	<meta
		name="twitter:image"
		content="https://www.olujohnsonbusinesstechnicalservices.com/4111232.png"
	/>

	<!-- Service-specific meta tags -->
	<meta name="service:category" content="IT Services" />
	<meta name="service:area" content="West Africa" />
	<meta name="service:type" content="Hardware Repair, Software Development" />

	<!-- JSON-LD Structured Data for Services -->
	<script type="application/ld+json">
		{
			"@context": "https://schema.org",
			"@type": "Service",
			"name": "IT Services & Hardware Repair",
			"description": "Professional IT services including printer repair, computer maintenance, cheque encoder service, and custom software development. Serving banks, offices, and institutions across West Africa.",
			"url": "https://www.olujohnsonbusinesstechnicalservices.com/Services",
			"image": "https://www.olujohnsonbusinesstechnicalservices.com/4111232.png",
			"provider": {
				"@type": "Organization",
				"name": "Olu Johnson Business Technical Services",
				"url": "https://www.olujohnsonbusinesstechnicalservices.com"
			},
			"serviceType": "IT Services",
			"areaServed": [
				{
					"@type": "Country",
					"name": "Nigeria"
				},
				{
					"@type": "Country",
					"name": "Ghana"
				},
				{
					"@type": "Country",
					"name": "Sierra Leone"
				},
				{
					"@type": "Country",
					"name": "Liberia"
				},
				{
					"@type": "Country",
					"name": "Gambia"
				},
				{
					"@type": "Country",
					"name": "Senegal"
				},
				{
					"@type": "Country",
					"name": "Mali"
				},
				{
					"@type": "Country",
					"name": "Burkina Faso"
				},
				{
					"@type": "Country",
					"name": "Niger"
				},
				{
					"@type": "Country",
					"name": "Chad"
				},
				{
					"@type": "Country",
					"name": "Cameroon"
				},
				{
					"@type": "Country",
					"name": "Benin"
				},
				{
					"@type": "Country",
					"name": "Togo"
				},
				{
					"@type": "Country",
					"name": "Ivory Coast"
				},
				{
					"@type": "Country",
					"name": "Guinea"
				},
				{
					"@type": "Country",
					"name": "Guinea-Bissau"
				},
				{
					"@type": "Country",
					"name": "Cape Verde"
				},
				{
					"@type": "Country",
					"name": "Mauritania"
				}
			],
			"hasOfferCatalog": {
				"@type": "OfferCatalog",
				"name": "IT Services Catalog",
				"itemListElement": [
					{
						"@type": "Offer",
						"itemOffered": {
							"@type": "Service",
							"name": "Printer Repair",
							"description": "Certified repairs for HP, Canon, Epson, and more printer brands"
						}
					},
					{
						"@type": "Offer",
						"itemOffered": {
							"@type": "Service",
							"name": "Cheque Encoder Service",
							"description": "Maintenance and support for cheque encoding devices"
						}
					},
					{
						"@type": "Offer",
						"itemOffered": {
							"@type": "Service",
							"name": "On-Site Support",
							"description": "Fast response for urgent hardware issues"
						}
					},
					{
						"@type": "Offer",
						"itemOffered": {
							"@type": "Service",
							"name": "Custom Software Development",
							"description": "Tailored software solutions including Tasmal x Cheque Encoder"
						}
					},
					{
						"@type": "Offer",
						"itemOffered": {
							"@type": "Service",
							"name": "Integration Services",
							"description": "Seamless software integration for your workflow"
						}
					}
				]
			},
			"audience": {
				"@type": "Audience",
				"audienceType": "Banks, Offices, Financial Institutions, Government Agencies"
			},
			"keywords": "IT services, hardware repair, printer repair, computer repair, cheque encoder service, custom software development, West Africa, Nigeria, Lagos, banking IT support, office equipment repair"
		}
	</script>
</svelte:head>

<!-- Breadcrumb -->
<BreadCrumb />

<!-- Main Content -->
<main class="container mx-auto px-4">
	<!--Services Hero -->
	<section
		class="rounded-lg bg-gradient-to-r bg-[url('/purple-Bg.jpg')] from-purple-500 via-purple-400 to-purple-300 bg-cover py-10"
	>
		<div class="container mx-auto flex flex-col items-center justify-between px-4 md:flex-row">
			<!-- Text Content -->
			<div class="animate-fade-in mb-8 md:mb-0 md:w-1/2">
				<h2 class="mb-6 text-4xl font-bold text-white md:text-5xl">Our Services</h2>
				<p class="mb-8 max-w-lg text-xl text-white">
					Comprehensive hardware repair and custom software solutions for banks, offices, and
					institutions.
				</p>
			</div>

			<!-- Image Section -->
			<div
				class="animate-fade-out relative h-[300px] w-full rounded-lg bg-cover md:h-[400px] md:w-1/2"
				style="background-image: url('/4111232.png');"
			>
				<!-- <img
					src="/4111232.png"
					alt="services-hero"
					class="md:h-[400px] h-full w-full bg-cover rounded-lg object-cover shadow-lg"
				/> -->
				<div class="absolute inset-0 rounded-lg bg-black opacity-5"></div>
			</div>
		</div>
	</section>

	<!-- Hardware Repair Section -->
	<section class="by-gray-100 my-10">
		<h2 class="mb-6 text-2xl font-bold text-blue-600">Hardware Repair</h2>
		<div class="grid grid-cols-1 gap-8 md:grid-cols-3">
			<!-- Printer Repair -->
			<div
				class="grid transform rounded-lg bg-gray-100 p-6 shadow-md transition duration-300 hover:scale-105"
			>
				<!--Icon  -->
				<div class="mb-4 flex text-gray-100">
					<span class="rounded-full bg-purple-600 p-1"><PrinterIcon /></span>
				</div>
				<div>
					<h3 class="mb-2 text-xl font-bold">Printer Repair</h3>
					<p class="mb-4">Certified repairs for HP, Canon, Epson, and more.</p>
				</div>
				<div>
					<a
						href="#"
						class="rounded bg-purple-600 px-4 py-2 font-bold text-white transition hover:bg-purple-700"
						>Request Repair</a
					>
				</div>
			</div>

			<!-- Cheque Encoder Service -->
			<div
				class=" grid transform rounded-lg bg-gray-100 p-6 shadow-md transition duration-300 hover:scale-105"
			>
				<div class="mb-4 flex text-gray-100">
					<span class="rounded-full bg-purple-600 p-1"> <CreditCardIcon /> </span>
				</div>
				<div>
					<h3 class="mb-2 text-xl font-bold">Cheque Encoder Service</h3>
					<p class="mb-4">Maintenance and support for cheque encoding devices.</p>
				</div>
				<div>
					<a
						href="#"
						class="rounded bg-purple-600 px-4 py-2 font-bold text-white transition hover:bg-purple-700"
						>Book Service</a
					>
				</div>
			</div>

			<!-- On-Site Support -->
			<div
				class="grid transform rounded-lg bg-gray-100 p-6 shadow-md transition duration-300 hover:scale-105"
			>
				<div>
					<div class="mb-4 flex text-gray-100">
						<span class="rounded-full bg-purple-600 p-1"> <HeadphonesIcon /> </span>
					</div>
				</div>

				<div>
					<h3 class="mb-2 text-xl font-bold">On-Site Support</h3>
					<p class="mb-4">Fast response for urgent hardware issues.</p>
				</div>

				<div>
					<a
						href="#"
						class="rounded bg-purple-600 px-4 py-2 font-bold text-white transition hover:bg-purple-700"
						>Contact Team</a
					>
				</div>
			</div>
		</div>
	</section>

	<!-- Custom Software Section -->
	<section class="mb-10">
		<h2 class="mb-6 text-2xl font-bold text-blue-600">Custom Software</h2>
		<div class="grid grid-cols-1 gap-8 md:grid-cols-2">
			<!-- Tasmal x Encoder -->
			<div
				class="transform rounded-lg bg-purple-50 p-6 shadow-md transition duration-300 hover:scale-105"
			>
				<div class="mb-4 flex items-center justify-start text-gray-100">
					<span class="rounded-full bg-purple-600 p-1"><ShieldIcon /></span>
				</div>
				<h3 class="mb-2 text-xl font-bold">Tasmal x Encoder</h3>
				<p class="mb-4">Secure cheque encoding for banks and institutions.</p>
				<a
					href="#"
					class="rounded bg-purple-600 px-4 py-2 font-bold text-white transition hover:bg-purple-700"
					>Learn More</a
				>
			</div>

			<!-- Integration Services -->
			<div
				class="transform rounded-lg bg-purple-100 p-6 shadow-md transition duration-300 hover:scale-105"
			>
				<div class="mb-4 flex items-center justify-start text-gray-100">
					<span class="rounded-full bg-purple-600 p-1"><LinkIcon /></span>
				</div>
				<h3 class="mb-2 text-xl font-bold">Integration Services</h3>
				<p class="mb-4">Seamless software integration for your workflow.</p>
				<a
					href="#"
					class="rounded bg-purple-600 px-4 py-2 font-bold text-white transition hover:bg-purple-700"
					>Get Started</a
				>
			</div>
		</div>
	</section>

	<!-- How It Works Section -->
	<section class="mb-10">
		<h2 class="mb-6 text-2xl font-bold text-blue-600">How It Works</h2>
		<div class="grid grid-cols-1 gap-8 md:grid-cols-3">
			<!-- Consultation -->
			<div
				class="transform rounded-lg bg-gray-100 p-6 shadow-md transition duration-300 hover:scale-105"
			>
				<div class="mb-4 flex text-gray-100">
					<span class="rounded-full bg-purple-600 p-1"><PhoneIncomingIcon /></span>
				</div>
				<h3 class="mb-2 text-xl font-bold">1. Consultation</h3>
				<p class="mb-4">Discuss your needs with our experts.</p>
			</div>

			<!-- Service Delivery -->
			<div
				class="transform rounded-lg bg-purple-100 p-6 shadow-md transition duration-300 hover:scale-105"
			>
				<div class="mb-4 flex text-gray-100">
					<span class="rounded-full bg-purple-600 p-1"><TruckIcon /></span>
				</div>
				<h3 class="mb-2 text-xl font-bold">2. Service Delivery</h3>
				<p class="mb-4">Certified technicians handle your request.</p>
			</div>

			<!-- Quality Assurance -->
			<div
				class="transform rounded-lg bg-purple-50 p-6 shadow-md transition duration-300 hover:scale-105"
			>
				<div class="mb-4 flex text-gray-100">
					<span class="rounded-full bg-purple-600 p-1"><ThumbsUpIcon /></span>
				</div>
				<h3 class="mb-2 text-xl font-bold">3. Quality Assurance</h3>
				<p class="mb-4">Every service is tested and guaranteed.</p>
			</div>
		</div>
	</section>
</main>

<!-- Footer -->
<Footer />
<link
	rel="stylesheet"
	href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css"
	integrity="sha512-pV1ytoZ7vJfxUjKzZqMkFfI5g9HcZmQ1rGexl+yGzZJRYuY1o8bFzaoLwFBO+NqE5g=="
	crossorigin="anonymous"
	referrerpolicy="no-referrer"
/>

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

	@keyframes fadeOut {
		from {
			opacity: 0;
			transform: translateY(-20px);
		}
		to {
			opacity: 1;
			transform: translateY(0);
		}
	}

	.animate-fade-out {
		animation: fadeOut 1s ease-out forwards;
	}
</style>
