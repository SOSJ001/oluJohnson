<script>
	import BreadCrumb from '$lib/components/BreadCrumb.svelte';
	import Footer from '$lib/components/Footer.svelte';

	const brands = [
		{
			name: 'HP',
			services: 'Printers, Scanners, Cheque Encoders',
			icon: 'fas fa-print',
			logo: 'https://cdn.brandfetch.io/idntgPecbn/theme/dark/logo.svg?c=1bxid64Mup7aczewSAYMX&t=1750316474215'
		},
		{
			name: 'Canon',
			services: 'Printers, Scanners',
			icon: 'fas fa-camera',
			logo: 'https://cdn.brandfetch.io/idsU6MactO/theme/dark/logo.svg?c=1bxid64Mup7aczewSAYMX&t=1675855846514'
		},
		{
			name: 'Epson',
			services: 'Cheque Encoders, Printers',
			icon: 'fas fa-check-square',
			logo: 'https://cdn.brandfetch.io/idGfYS68w5/w/420/h/100/theme/dark/logo.png?c=1bxid64Mup7aczewSAYMX&t=1750361229276'
		},
		{
			name: 'Dell',
			services: 'Workstations, Laptops',
			icon: 'fas fa-desktop',
			logo: 'https://cdn.brandfetch.io/idc1hWCJYN/w/400/h/400/theme/dark/icon.png?c=1bxid64Mup7aczewSAYMX&t=1721282612101'
		},
		{
			name: 'Lenovo',
			services: 'Laptops, Desktops',
			icon: 'fas fa-laptop',
			logo: 'https://cdn.brandfetch.io/iddtMrgJvA/theme/dark/logo.svg?c=1bxid64Mup7aczewSAYMX&t=1667571542988'
		},
		{
			name: 'Panasonic',
			services: 'Scanners, Printers',
			icon: 'fas fa-cogs',
			logo: 'https://cdn.brandfetch.io/idZc2Ve3u9/theme/dark/logo.svg?c=1bxid64Mup7aczewSAYMX&t=1667564190785'
		},
		{
			name: 'Okidata',
			services: 'Printers, Scanners',
			icon: 'fas fa-print',
			logo: 'https://cdn.brandfetch.io/id5HmsiXjY/w/576/h/168/theme/light/logo.png?c=1bxid64Mup7aczewSAYMX&t=1691149220831'
		},
		{
			name: 'Konica Minolta',
			services: 'Printers, Scanners, Copiers',
			icon: 'fas fa-print',
			logo: 'https://cdn.brandfetch.io/id9rHYuWzR/theme/dark/logo.svg?c=1bxid64Mup7aczewSAYMX&t=1691135442970'
		},
		{
			name: 'Xerox',
			services: 'Copiers, Printers, Document Management',
			icon: 'fas fa-copy',
			logo: 'https://cdn.brandfetch.io/id-RGKzn_O/theme/dark/logo.svg?c=1bxid64Mup7aczewSAYMX&t=1679467841459'
		},
		{
			name: 'Sharp',
			services: 'Copiers, Printers, Scanners',
			icon: 'fas fa-copy',
			logo: 'https://cdn.brandfetch.io/idOszzkauu/w/400/h/400/theme/dark/icon.png?c=1bxid64Mup7aczewSAYMX&t=1668517580639'
		},
		{
			name: 'Zebra',
			services: 'Label Printers, Barcode Printers, Mobile Printers',
			icon: 'fas fa-barcode',
			logo: '/logo-zebra-chat.png'
		},
		{
			name: 'Dymo',
			services: 'Label Printers, Tape Printers',
			icon: 'fas fa-tag',
			logo: '/Dymo-logo.svg'
		}
	];
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
			{#each brands as brand}
				<div
					class="transform rounded-lg bg-white p-6 shadow-md transition duration-300 hover:scale-105"
				>
					<div class="mb-4 flex items-center justify-center text-purple-500">
						{#if brand.logo}
							<img src={brand.logo} class="h-[36px]" alt="{brand.name} Logo" />
						{:else}
							<i class="{brand.icon} text-4xl"></i>
						{/if}
					</div>
					<h3 class="mb-2 text-xl font-bold">{brand.name}</h3>
					<p class="mb-4">{brand.services}</p>
				</div>
			{/each}
		</div>
	</section>

	<!-- Call-to-Action -->
	<section class="mb-10">
		<p class="mb-6 text-lg">
			Don’t see your brand? Contact us for support with additional manufacturers.
		</p>
		<a
			href="mailto:service.engineer@olujohnsonbusinesstechnicalservices.com"
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
