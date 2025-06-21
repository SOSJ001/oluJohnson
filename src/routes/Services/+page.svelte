<script>
	// @ts-ignore
	import BreadCrumb from '$lib/components/BreadCrumb.svelte';
	import Footer from '$lib/components/Footer.svelte';
	import { CreditCardIcon, HeadphonesIcon, PrinterIcon } from 'svelte-feather-icons';
</script>

<!-- Breadcrumb -->
<BreadCrumb />

<!-- Main Content -->
<main class="container mx-auto px-4">
	<!--Services Hero -->
	<section
		class="relative rounded-lg bg-gradient-to-r from-purple-500 via-purple-400 to-purple-300 py-10"
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
	<section class="my-10 by-gray-100">
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
				<div class="mb-4 flex items-center justify-center text-purple-500">
					<i class="fas fa-shield-alt text-4xl"></i>
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
				class="bg-purple-100 transform rounded-lg p-6 shadow-md transition duration-300 hover:scale-105"
			>
				<div class="mb-4 flex items-center justify-center text-purple-500">
					<i class="fas fa-code-branch text-4xl"></i>
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
				<div class="mb-4 flex items-center justify-center text-purple-500">
					<i class="fas fa-phone-alt text-4xl"></i>
				</div>
				<h3 class="mb-2 text-xl font-bold">1. Consultation</h3>
				<p class="mb-4">Discuss your needs with our experts.</p>
			</div>

			<!-- Service Delivery -->
			<div
				class="transform rounded-lg bg-purple-100 p-6 shadow-md transition duration-300 hover:scale-105"
			>
				<div class="mb-4 flex items-center justify-center text-purple-500">
					<i class="fas fa-users text-4xl"></i>
				</div>
				<h3 class="mb-2 text-xl font-bold">2. Service Delivery</h3>
				<p class="mb-4">Certified technicians handle your request.</p>
			</div>

			<!-- Quality Assurance -->
			<div
				class="transform rounded-lg bg-purple-50 p-6 shadow-md transition duration-300 hover:scale-105"
			>
				<div class="mb-4 flex items-center justify-center text-purple-500">
					<i class="fas fa-shield-check text-4xl"></i>
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
