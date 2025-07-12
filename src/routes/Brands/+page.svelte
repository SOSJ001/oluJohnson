<script>
	import BreadCrumb from '$lib/components/BreadCrumb.svelte';
	import Footer from '$lib/components/Footer.svelte';
</script>

<BreadCrumb />
<!-- Main Content -->
<main class="container mx-auto px-4">
	<!-- Header -->
	<section
		style="background-image: url('/purple-Bg.jpg');"
		class="relative mb-5 rounded-lg bg-gray-800 bg-cover bg-no-repeat px-3 py-6 text-gray-200 md:px-10 md:py-20"
	>
		<div class="animate-fade-in">
			<h1 class="mb-6 text-4xl font-bold md:text-5xl">Brands We Service</h1>
			<p class="text-lg">
				We expertly repair and support a wide range of leading hardware brands for offices, banks,
				and institutions.
			</p>
			<p>
				Our certified technicians use genuine parts and proven processes to ensure reliability and
				performance.
			</p>
		</div>
	</section>

	<!-- Major Brands Section -->
	<section class="mb-10">
		<h2 class="mb-6 text-2xl font-bold">Major Brands</h2>
		<div class="grid grid-cols-1 gap-6 md:grid-cols-3">
			<!-- HP -->
			<div
				class="transform rounded-lg bg-white p-6 shadow-md transition duration-300 hover:scale-105"
			>
				<div class="mb-4 flex items-center justify-center text-purple-500">
					<i class="fas fa-print text-4xl"><img src="/HP-Logo.png" class="h-[36px]" alt="" /></i>
				</div>
				<h3 class="mb-2 text-xl font-bold">HP</h3>
				<p class="mb-4">Printers, Scanners, Cheque Encoders</p>
			</div>

			<!-- Canon -->
			<div
				class="transform rounded-lg bg-white p-6 shadow-md transition duration-300 hover:scale-105"
			>
				<div class="mb-4 flex items-center justify-center text-purple-500">
					<i class="fas fa-camera text-4xl"></i>
				</div>
				<h3 class="mb-2 text-xl font-bold">Canon</h3>
				<p class="mb-4">Printers, Scanners</p>
			</div>

			<!-- Epson -->
			<div
				class="transform rounded-lg bg-white p-6 shadow-md transition duration-300 hover:scale-105"
			>
				<div class="mb-4 flex items-center justify-center text-purple-500">
					<i class="fas fa-check-square text-4xl"></i>
				</div>
				<h3 class="mb-2 text-xl font-bold">Epson</h3>
				<p class="mb-4">Cheque Encoders, Printers</p>
			</div>

			<!-- Dell -->
			<div
				class="transform rounded-lg bg-white p-6 shadow-md transition duration-300 hover:scale-105"
			>
				<div class="mb-4 flex items-center justify-center text-purple-500">
					<i class="fas fa-desktop text-4xl"></i>
				</div>
				<h3 class="mb-2 text-xl font-bold">Dell</h3>
				<p class="mb-4">Workstations, Laptops</p>
			</div>

			<!-- Lenovo -->
			<div
				class="transform rounded-lg bg-white p-6 shadow-md transition duration-300 hover:scale-105"
			>
				<div class="mb-4 flex items-center justify-center text-purple-500">
					<i class="fas fa-laptop text-4xl"></i>
				</div>
				<h3 class="mb-2 text-xl font-bold">Lenovo</h3>
				<p class="mb-4">Laptops, Desktops</p>
			</div>

			<!-- Fujitsu -->
			<div
				class="transform rounded-lg bg-white p-6 shadow-md transition duration-300 hover:scale-105"
			>
				<div class="mb-4 flex items-center justify-center text-purple-500">
					<i class="fas fa-file-contract text-4xl"></i>
				</div>
				<h3 class="mb-2 text-xl font-bold">Fujitsu</h3>
				<p class="mb-4">Scanners, Cheque Encoders</p>
			</div>

			<!-- Panasonic -->
			<div
				class="transform rounded-lg bg-white p-6 shadow-md transition duration-300 hover:scale-105"
			>
				<div class="mb-4 flex items-center justify-center text-purple-500">
					<i class="fas fa-cogs text-4xl"></i>
				</div>
				<h3 class="mb-2 text-xl font-bold">Panasonic</h3>
				<p class="mb-4">Scanners, Printers</p>
			</div>

			<!-- Magner -->
			<div
				class="transform rounded-lg bg-white p-6 shadow-md transition duration-300 hover:scale-105"
			>
				<div class="mb-4 flex items-center justify-center text-purple-500">
					<i class="fas fa-balance-scale text-4xl"></i>
				</div>
				<h3 class="mb-2 text-xl font-bold">Magner</h3>
				<p class="mb-4">Cheque Encoders</p>
			</div>

			<!-- Glory -->
			<div
				class="transform rounded-lg bg-white p-6 shadow-md transition duration-300 hover:scale-105"
			>
				<div class="mb-4 flex items-center justify-center text-purple-500">
					<i class="fas fa-money-bill-wave text-4xl"></i>
				</div>
				<h3 class="mb-2 text-xl font-bold">Glory</h3>
				<p class="mb-4">Banking Equipment</p>
			</div>
		</div>
	</section>

	<!-- Call-to-Action -->
	<section class="mb-10">
		<p class="mb-6 text-lg">
			Don’t see your brand? Contact us for support with additional manufacturers.
		</p>
		<a
			href="#"
			class="rounded bg-purple-600 px-6 py-3 font-bold text-white transition hover:bg-purple-700"
			>Request Brand Support</a
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
