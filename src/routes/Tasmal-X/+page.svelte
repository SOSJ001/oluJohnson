<script>
	import BreadCrumb from '$lib/components/BreadCrumb.svelte';
	import Footer from '$lib/components/Footer.svelte';
	import Icon from '$lib/components/icon.svelte';
	import {
		EditIcon,
		LayersIcon,
		LinkIcon,
		LockIcon,
		SettingsIcon,
		ShieldIcon
	} from 'svelte-feather-icons';
</script>

<BreadCrumb />

<!-- Main Content -->
<main class="container mx-auto px-4">
	<!-- Hero Section -->
	<section
		style="background-image: url('/purple-Bg.jpg');"
		class="relative mb-5 rounded-lg bg-gray-800 bg-cover bg-no-repeat px-3 py-6 text-gray-200 md:px-10 md:py-20"
	>
		<div class="animate-fade-in">
			<h1 class="mb-6 text-4xl font-bold md:text-5xl">Tasmal x Cheque Encoder</h1>
			<p class="mb-8 text-xl">
				Industry-leading cheque encoding software trusted by banks and institutions worldwide.
				Advanced security, seamless integration, and global compliance.
			</p>
			<div class="flex gap-4 text-center">
				<a
					href="#"
					class="rounded bg-purple-600 px-6 py-3 font-bold text-white transition hover:bg-purple-700"
					>Request Demo</a
				>
				<a
					href="#"
					class="rounded bg-white px-6 py-3 font-bold text-purple-600 shadow transition hover:bg-gray-100"
					>Contact Sales</a
				>
			</div>
		</div>
	</section>

	<!-- Tabs Navigation -->
	<nav class="mb-10 shadow">
		<ul class="flex space-x-5">
			<li>
				<a href="#features" class="border-b-2 border-purple-600 pb-1 text-lg font-medium"
					>Features</a
				>
			</li>
			<li>
				<a
					href="#system-requirements"
					class="border-b-2 border-transparent pb-1 text-lg font-medium hover:border-purple-600"
					>System Requirements</a
				>
			</li>
		</ul>
	</nav>

	<!-- Key Features -->
	<section id="features" class="mb-5">
		<h2 class="mb-6 text-2xl font-bold">Key Features</h2>
		<div class="grid grid-cols-1 gap-6 md:grid-cols-3">
			<!-- Accurate Encoding -->
			<div
				class="transform rounded-lg bg-white p-6 shadow-md transition duration-300 hover:scale-105"
			>
				<Icon>
					<span slot="icon">
						<LockIcon />
					</span>
				</Icon>
				<h3 class="mb-2 text-xl font-bold">Accurate Encoding</h3>
				<p class="mb-4">Ensures precise cheque data capture and encoding for all major banks.</p>
			</div>

			<!-- Seamless Integration -->
			<div
				class="transform rounded-lg bg-white p-6 shadow-md transition duration-300 hover:scale-105"
			>
				<Icon>
					<span slot="icon">
						<LinkIcon />
					</span>
				</Icon>
				<h3 class="mb-2 text-xl font-bold">Seamless Integration</h3>
				<p class="mb-4">Connects easily with core banking and document management systems.</p>
			</div>

			<!-- Advanced Security -->
			<div
				class="transform rounded-lg bg-white p-6 shadow-md transition duration-300 hover:scale-105"
			>
				<Icon>
					<span slot="icon">
						<ShieldIcon />
					</span>
				</Icon>
				<h3 class="mb-2 text-xl font-bold">Advanced Security</h3>
				<p class="mb-4">Multi-layer encryption and user access controls for compliance.</p>
			</div>

			<!-- Batch Processing -->
			<div
				class="transform rounded-lg bg-white p-6 shadow-md transition duration-300 hover:scale-105"
			>
				<Icon>
					<span slot="icon">
						<LayersIcon />
					</span>
				</Icon>
				<h3 class="mb-2 text-xl font-bold">Batch Processing</h3>
				<p class="mb-4">Process high volumes of cheques simultaneously with automated workflows.</p>
			</div>

			<!-- Customizable Templates -->
			<div
				class="transform rounded-lg bg-white p-6 shadow-md transition duration-300 hover:scale-105"
			>
				<Icon>
					<span slot="icon">
						<EditIcon />
					</span>
				</Icon>
				<h3 class="mb-2 text-xl font-bold">Customizable Templates</h3>
				<p class="mb-4">
					Adapt fields and layouts to match specific banking formats and requirements.
				</p>
			</div>

			<!-- Admin Priviledges -->
			<div
				class="transform rounded-lg bg-white p-6 shadow-md transition duration-300 hover:scale-105"
			>
				<Icon>
					<span slot="icon">
						<SettingsIcon />
					</span>
				</Icon>
				<h3 class="mb-2 text-xl font-bold">Admin Priviledges</h3>
				<p class="mb-4">Instant management of both active and Dormant Bank Branhes.</p>
			</div>
		</div>
	</section>
	<!-- System Requirements -->
	<section id="system-requirements" class="mb-5">
		<h2 class="mb-6 text-2xl font-bold">System Requirements</h2>
		<div class="overflow-x-auto">
			<table class="min-w-full divide-y divide-gray-200">
				<thead class="bg-gray-50">
					<tr>
						<th
							scope="col"
							class="px-6 py-3 text-left text-xs font-medium tracking-wider text-gray-500 uppercase sm:px-4 md:px-6 lg:px-8"
						>
							Component
						</th>
						<th
							scope="col"
							class="px-6 py-3 text-left text-xs font-medium tracking-wider text-gray-500 uppercase sm:px-4 md:px-6 lg:px-8"
						>
							Requirement
						</th>
					</tr>
				</thead>
				<tbody class="divide-y divide-gray-200 bg-white">
					<tr>
						<td class="px-6 py-4 whitespace-nowrap sm:px-4 md:px-6 lg:px-8">OS</td>
						<td class="px-6 py-4 whitespace-nowrap sm:px-4 md:px-6 lg:px-8"
							>Windows 10 pro or Windows 11 pro</td
						>
					</tr>
					<tr>
						<td class="px-6 py-4 whitespace-nowrap sm:px-4 md:px-6 lg:px-8">Processor</td>
						<td class="px-6 py-4 whitespace-nowrap sm:px-4 md:px-6 lg:px-8"
							>Intel i5 or equivalent (1.9 GHz+)</td
						>
					</tr>
					<tr>
						<td class="px-6 py-4 whitespace-nowrap sm:px-4 md:px-6 lg:px-8">Memory</td>
						<td class="px-6 py-4 whitespace-nowrap sm:px-4 md:px-6 lg:px-8"
							>8 GB RAM (16 GB recommended)</td
						>
					</tr>
					<tr>
						<td class="px-6 py-4 whitespace-nowrap sm:px-4 md:px-6 lg:px-8">Storage</td>
						<td class="px-6 py-4 whitespace-nowrap sm:px-4 md:px-6 lg:px-8"
							>250+ GB free space (HDD recommended)</td
						>
					</tr>
					<tr>
						<td class="px-6 py-4 whitespace-nowrap sm:px-4 md:px-6 lg:px-8">Peripherals</td>
						<td class="px-6 py-4 whitespace-nowrap sm:px-4 md:px-6 lg:px-8"
							>MICR-enabled cheque scanner</td
						>
					</tr>
				</tbody>
			</table>
		</div>
	</section>

	<!-- Visual Demonstration -->
	<section class="mb-5">
		<h2 class="mb-6 text-2xl font-bold">See Tasmal x in Action</h2>
		<img
			loading="lazy"
			src="/Tasmal-X_overview.png"
			alt="Tasmal x in Action"
			class="h-full w-full rounded-lg object-cover shadow-lg"
		/>
	</section>

	<!-- Call-to-Action -->
	<section class="mb-5">
		<h2 class="mb-6 text-2xl font-bold">Ready to transform your cheque processing?</h2>
		<div class="flex gap-4">
			<a
				href="#"
				class="rounded bg-purple-600 px-6 py-3 font-bold text-white transition hover:bg-purple-700"
				>Request Demo</a
			>
			<a
				href="#"
				class="rounded bg-white px-6 py-3 font-bold text-purple-600 shadow transition hover:bg-gray-100"
				>Contact Sales</a
			>
		</div>
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
