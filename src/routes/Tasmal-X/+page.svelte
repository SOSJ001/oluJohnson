<script lang="ts">
	import { env } from '$env/dynamic/public';
	import { slide } from 'svelte/transition';
	import BreadCrumb from '$lib/components/BreadCrumb.svelte';
	import Footer from '$lib/components/Footer.svelte';
	import Icon from '$lib/components/icon.svelte';
	import {
		EditIcon,
		LayersIcon,
		LinkIcon,
		LockIcon,
		SettingsIcon,
		ShieldIcon,
		FileTextIcon,
		DownloadIcon,
		CheckCircleIcon,
		AlertCircleIcon
	} from 'svelte-feather-icons';

	// SEO Meta Tags for Tasmal X page
	import { page } from '$app/stores';

	// Form state management
	let formSubmitting = false;
	let formSubmitted = false;
	let formError = '';
	let showForm = true;
	let successMessageRef: HTMLDivElement;
	let renewalProcessRef: HTMLDivElement;

	// Google Sheets via Apps Script configuration
	// Get from environment variable (set in .env file)
	const GOOGLE_SHEETS_WEB_APP_URL = env.PUBLIC_GOOGLE_SHEETS_WEB_APP_URL || '';

	// Hide form when submitted successfully
	$: if (formSubmitted) {
		setTimeout(() => {
			showForm = false;
			// Scroll to Renewal Process section after form collapses
			setTimeout(() => {
				if (renewalProcessRef) {
					renewalProcessRef.scrollIntoView({ behavior: 'smooth', block: 'start' });
				}
			}, 100);
		}, 300); // Small delay to show submission animation
	}

	function resetForm() {
		formSubmitted = false;
		formError = '';
		showForm = true;
	}

	async function handleFormSubmit(event: SubmitEvent) {
		event.preventDefault();
		formSubmitting = true;
		formError = '';

		const form = event.target as HTMLFormElement | null;
		if (!form) return;

		const formData = new FormData(form);
		const data = {
			organization: formData.get('organization'),
			primaryContact: formData.get('primary-contact'),
			physicalAddress: formData.get('physical-address'),
			email: formData.get('email'),
			phone: formData.get('phone'),
			serialNumber: formData.get('serial-number'),
			hardwareId: formData.get('hardware-id'),
			operatingSystem: formData.get('operating-system'),
			installationSite: formData.get('installation-site'),
			licenseTerm: formData.get('license-term'),
			currentLicense: formData.get('current-license') || 'Not provided',
			currentLicenseStartDate: formData.get('current-license-start-date') || 'Not provided',
			currentLicenseExpirationDate:
				formData.get('current-license-expiration-date') || 'Not provided',
			additionalNotes: formData.get('additional-notes') || 'None'
		};

		try {
			// Option 1: Google Sheets via Apps Script (RECOMMENDED - No redirect, unlimited, free)
			// Uses environment variable from .env file
			if (
				GOOGLE_SHEETS_WEB_APP_URL &&
				GOOGLE_SHEETS_WEB_APP_URL !== 'YOUR_GOOGLE_APPS_SCRIPT_WEB_APP_URL'
			) {
				const response = await fetch(GOOGLE_SHEETS_WEB_APP_URL, {
					method: 'POST',
					mode: 'no-cors', // Required for Google Apps Script
					headers: {
						'Content-Type': 'application/json'
					},
					body: JSON.stringify({
						organization: data.organization,
						primaryContact: data.primaryContact,
						physicalAddress: data.physicalAddress,
						email: data.email,
						phone: data.phone,
						serialNumber: data.serialNumber,
						hardwareId: data.hardwareId,
						operatingSystem: data.operatingSystem,
						installationSite: data.installationSite,
						licenseTerm: data.licenseTerm,
						currentLicense: data.currentLicense,
						currentLicenseStartDate: data.currentLicenseStartDate,
						currentLicenseExpirationDate: data.currentLicenseExpirationDate,
						additionalNotes: data.additionalNotes,
						timestamp: new Date().toISOString()
					})
				});

				formSubmitted = true;
				form.reset();
				return;
			}

			// Fallback: Using mailto (opens email client)
			const mailtoBody = `Tasmal X License Renewal Request

CLIENT IDENTIFICATION:
Organization: ${data.organization}
Primary Contact: ${data.primaryContact}
Physical Address: ${data.physicalAddress}
Email: ${data.email}
Phone: ${data.phone}

HARDWARE & SYSTEM IDENTIFIERS:
- Motherboard Serial Number: ${data.serialNumber}
- Processor / Machine ID: ${data.hardwareId}
- Operating System: ${data.operatingSystem}
- Installation Site / Branch: ${data.installationSite}

CURRENT LICENSE DETAILS:
- Requested License Term: ${data.licenseTerm === '7d' ? '7 days' : `${data.licenseTerm} year(s)`}
- Current Activation Key: ${data.currentLicense}
- Current License Start Date: ${data.currentLicenseStartDate}
- Current License Expiration Date: ${data.currentLicenseExpirationDate}

Additional Notes: ${data.additionalNotes}`;

			window.location.href = `mailto:service.engineer@olujohnsonbusinesstechnicalservices.com?subject=Tasmal X License Renewal Request&body=${encodeURIComponent(mailtoBody)}`;

			formSubmitted = true;
			form.reset();
		} catch (error) {
			console.error('Form submission error:', error);
			formError = 'Failed to submit form. Please try again or contact support directly.';
		} finally {
			formSubmitting = false;
		}
	}
</script>

<!-- Page-specific SEO Meta Tags -->
<svelte:head>
	<title>
		Tasmal x Cheque Encoder - Advanced Banking Software | Olu Johnson Business Technical Services
	</title>
	<!-- Enhanced SEO for Tasmal X -->
	<meta
		name="description"
		content="Tasmal x Cheque Encoder - Industry-leading cheque encoding software with advanced security, MICR encoding, multi-bank support, and global compliance. Trusted by banks worldwide."
	/>
	<meta
		name="keywords"
		content="Tasmal x, cheque encoder, MICR encoding, banking software, cheque processing, financial software, bank automation, cheque security, banking compliance, West Africa, Nigeria, Lagos"
	/>

	<!-- Open Graph for Tasmal X -->
	<meta property="og:title" content="Tasmal x Cheque Encoder - Advanced Banking Software" />
	<meta
		property="og:description"
		content="Industry-leading cheque encoding software with advanced security, MICR encoding, multi-bank support, and global compliance. Trusted by banks worldwide."
	/>
	<meta property="og:type" content="product" />
	<meta
		property="og:image"
		content="https://www.olujohnsonbusinesstechnicalservices.com/Tasmal-X_overview.png"
	/>
	<meta property="og:url" content="https://www.olujohnsonbusinesstechnicalservices.com/Tasmal-X" />

	<!-- Twitter Card for Tasmal X -->
	<meta name="twitter:card" content="summary_large_image" />
	<meta name="twitter:title" content="Tasmal x Cheque Encoder - Advanced Banking Software" />
	<meta
		name="twitter:description"
		content="Industry-leading cheque encoding software with advanced security, MICR encoding, multi-bank support, and global compliance."
	/>
	<meta
		name="twitter:image"
		content="https://www.olujohnsonbusinesstechnicalservices.com/Tasmal-X_overview.png"
	/>

	<!-- Product-specific meta tags -->
	<meta name="product:name" content="Tasmal x Cheque Encoder" />
	<meta name="product:category" content="Banking Software" />
	<meta name="product:brand" content="Olu Johnson Business Technical Services" />

	<!-- JSON-LD Structured Data for Tasmal X Product -->
	<script type="application/ld+json">
		{
			"@context": "https://schema.org",
			"@type": "SoftwareApplication",
			"name": "Tasmal x Cheque Encoder",
			"description": "Industry-leading cheque encoding software with advanced security, MICR encoding, multi-bank support, and global compliance. Trusted by banks and financial institutions worldwide.",
			"url": "https://www.olujohnsonbusinesstechnicalservices.com/Tasmal-X",
			"image": "https://www.olujohnsonbusinesstechnicalservices.com/Tasmal-X_overview.png",
			"applicationCategory": "BusinessApplication",
			"operatingSystem": "Windows",
			"softwareVersion": "2.0",
			"datePublished": "2023-01-01",
			"dateModified": "2024-01-15",
			"author": {
				"@type": "Organization",
				"name": "Olu Johnson Business Technical Services",
				"url": "https://www.olujohnsonbusinesstechnicalservices.com"
			},
			"offers": {
				"@type": "Offer",
				"priceCurrency": "USD",
				"availability": "https://schema.org/InStock",
				"price": "Contact for pricing",
				"priceValidUntil": "2025-12-31"
			},
			"featureList": [
				"Automated MICR Line Encoding",
				"Multi-bank & Multi-user Support",
				"Integrated Security Protocols",
				"Compliance with Global Banking Standards",
				"Real-time Processing",
				"Audit Trail & Reporting",
				"User Role Management",
				"Data Encryption"
			],
			"systemRequirements": {
				"@type": "TechArticle",
				"about": "System Requirements",
				"text": "Windows 10+, .NET Framework 4.8+, SQL Server Express, 4GB RAM minimum, 2GB free disk space"
			},
			"audience": {
				"@type": "Audience",
				"audienceType": "Banks, Financial Institutions, Credit Unions"
			},
			"keywords": "cheque encoder, MICR encoding, banking software, financial software, bank automation, cheque processing, banking compliance"
		}
	</script>
</svelte:head>

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
			<div class="flex flex-col gap-4 text-center sm:flex-row sm:flex-wrap">
				<a
					href="mailto:service.engineer@olujohnsonbusinesstechnicalservices.com"
					class="w-full rounded bg-purple-600 px-6 py-3 font-bold text-white transition hover:bg-purple-700 sm:w-auto"
					>Request Demo</a
				>
				<a
					href="tel:+23278220326"
					class="w-full rounded bg-white px-6 py-3 font-bold text-purple-600 shadow transition hover:bg-gray-100 sm:w-auto"
					>Contact Sales</a
				>
				<a
					href="#license-renewal"
					class="w-full rounded border-2 border-white bg-transparent px-6 py-3 font-bold text-white transition hover:bg-white hover:text-purple-600 sm:w-auto"
					>License Renewal</a
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
			<li>
				<a
					href="#license-renewal"
					class="border-b-2 border-transparent pb-1 text-lg font-medium hover:border-purple-600"
					>License Renewal</a
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

			<!-- Admin Privileges -->
			<div
				class="transform rounded-lg bg-white p-6 shadow-md transition duration-300 hover:scale-105"
			>
				<Icon>
					<span slot="icon">
						<SettingsIcon />
					</span>
				</Icon>
				<h3 class="mb-2 text-xl font-bold">Admin Privileges</h3>
				<p class="mb-4">Instant management of both active and Dormant Bank Branches.</p>
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

	<!-- License Renewal Section -->
	<section id="license-renewal" class="mb-5">
		<h2 class="mb-6 text-xl font-bold sm:text-2xl">Tasmal X License Renewal Process</h2>

		<!-- Important Notice -->
		<div class="mb-6 rounded-lg border-l-4 border-yellow-500 bg-yellow-50 p-4 sm:p-6">
			<div class="flex items-start">
				<AlertCircleIcon class="mt-0.5 mr-3 h-5 w-5 flex-shrink-0 text-yellow-600" />
				<div class="min-w-0 flex-1">
					<h3 class="mb-2 text-base font-semibold text-yellow-800 sm:text-lg">
						Important: Grace Period Notice
					</h3>
					<p class="text-sm text-yellow-700 sm:text-base">
						Users are encouraged to submit renewal requests <strong>30 days prior to expiry</strong>
						to ensure a seamless transition before the <strong>60-day grace period</strong> concludes.
					</p>
				</div>
			</div>
		</div>

		<!-- Process Steps -->
		<div bind:this={renewalProcessRef} class="mb-8">
			<h3 class="mb-4 text-lg font-semibold sm:text-xl">Renewal Process</h3>
			<div class="grid grid-cols-1 gap-4 sm:gap-6 md:grid-cols-3">
				<!-- Step 1 -->
				<div
					class="transform rounded-lg bg-white p-4 shadow-md transition duration-300 hover:scale-105 sm:p-6"
				>
					<div class="mb-4 flex items-center justify-center">
						<div class="rounded-full bg-purple-100 p-2 sm:p-3">
							<FileTextIcon class="h-5 w-5 text-purple-600 sm:h-6 sm:w-6" />
						</div>
					</div>
					<h4 class="mb-2 text-base font-bold sm:text-lg">1. Identify Hardware</h4>
					<p class="text-sm text-gray-600 sm:text-base">
						Open Tasmal X and navigate to the <strong>Product Activation</strong> screen to retrieve
						your machine-specific <strong>Serial Number</strong> and <strong>Hardware ID</strong>.
					</p>
				</div>

				<!-- Step 2 -->
				<div
					class="transform rounded-lg bg-white p-4 shadow-md transition duration-300 hover:scale-105 sm:p-6"
				>
					<div class="mb-4 flex items-center justify-center">
						<div class="rounded-full bg-purple-100 p-2 sm:p-3">
							<DownloadIcon class="h-5 w-5 text-purple-600 sm:h-6 sm:w-6" />
						</div>
					</div>
					<h4 class="mb-2 text-base font-bold sm:text-lg">2. Submit Request</h4>
					<p class="text-sm text-gray-600 sm:text-base">
						Complete the <strong>Official License Renewal Request</strong> form below. You'll receive
						a confirmation email copy automatically for your records.
					</p>
				</div>

				<!-- Step 3 -->
				<div
					class="transform rounded-lg bg-white p-4 shadow-md transition duration-300 hover:scale-105 sm:p-6"
				>
					<div class="mb-4 flex items-center justify-center">
						<div class="rounded-full bg-purple-100 p-2 sm:p-3">
							<CheckCircleIcon class="h-5 w-5 text-purple-600 sm:h-6 sm:w-6" />
						</div>
					</div>
					<h4 class="mb-2 text-base font-bold sm:text-lg">3. Security Binding</h4>
					<p class="text-sm text-gray-600 sm:text-base">
						All licenses are <strong>machine-specific</strong>; ensure the hardware identifiers
						match the terminal intended for cheque production.
					</p>
				</div>
			</div>
		</div>

		<!-- Download Section - Commented out, using online form only -->
		<!-- <div class="mb-8 rounded-lg bg-gray-50 p-4 sm:p-6">
			<div class="mb-4 flex items-center">
				<FileTextIcon class="mr-3 h-5 w-5 flex-shrink-0 text-purple-600 sm:h-6 sm:w-6" />
				<h3 class="text-lg font-semibold sm:text-xl">Download Official Renewal Form</h3>
			</div>
			<p class="mb-4 text-sm text-gray-700 sm:text-base">
				Download the fillable PDF form that you can print, sign, and stamp. This form is suitable
				for official documentation and record-keeping.
			</p>
			<a
				href="/Tasmal-X-License-Renewal-Form.pdf"
				download
				class="inline-flex w-full items-center justify-center rounded bg-purple-600 px-6 py-3 text-sm font-semibold text-white transition hover:bg-purple-700 sm:w-auto"
			>
				<DownloadIcon class="mr-2 h-5 w-5" />
				Download PDF Form
			</a>
		</div> -->

		<!-- Online Form Section -->
		<div class="mb-8 rounded-lg bg-white p-4 shadow-md sm:p-6">
			<div class="mb-4 flex items-center">
				<EditIcon class="mr-3 h-5 w-5 flex-shrink-0 text-purple-600 sm:h-6 sm:w-6" />
				<h3 class="text-lg font-semibold sm:text-xl">Submit Online Renewal Request</h3>
			</div>
			<p class="mb-6 text-sm text-gray-700 sm:text-base">
				Complete the form below with your hardware information. All fields are required for security
				verification.
			</p>

			<!-- Success Message -->
			{#if formSubmitted}
				<div
					bind:this={successMessageRef}
					transition:slide={{ duration: 400 }}
					class="mb-6 rounded-lg border-l-4 border-green-500 bg-green-50 p-4"
				>
					<div class="flex items-start">
						<CheckCircleIcon class="mt-0.5 mr-3 h-5 w-5 flex-shrink-0 text-green-600" />
						<div class="min-w-0 flex-1">
							<h4 class="mb-1 text-sm font-semibold text-green-800">
								Request Submitted Successfully! ✅
							</h4>
							<p class="mb-4 text-xs text-green-700 sm:text-sm">
								Your license renewal request has been sent. We'll process it and contact you
								shortly.
							</p>
							<button
								type="button"
								on:click={resetForm}
								class="text-xs font-medium text-green-800 underline hover:text-green-900 sm:text-sm"
							>
								Submit Another Request
							</button>
						</div>
					</div>
				</div>
			{/if}

			<!-- Error Message -->
			{#if formError}
				<div class="mb-6 rounded-lg border-l-4 border-red-500 bg-red-50 p-4">
					<div class="flex items-start">
						<AlertCircleIcon class="mt-0.5 mr-3 h-5 w-5 flex-shrink-0 text-red-600" />
						<div class="min-w-0 flex-1">
							<p class="text-xs text-red-700 sm:text-sm">{formError}</p>
						</div>
					</div>
				</div>
			{/if}

			{#if showForm}
				<form transition:slide={{ duration: 400 }} on:submit={handleFormSubmit} class="space-y-6">
					<!-- Client Identification Section -->
					<div class="rounded-lg border-2 border-blue-200 bg-blue-50 p-4 sm:p-6">
						<h4 class="mb-4 text-base font-semibold text-blue-900 sm:text-lg">
							Client Identification
						</h4>
						<div class="space-y-4">
							<div>
								<label
									for="organization"
									class="mb-2 block text-xs font-medium text-gray-700 sm:text-sm"
								>
									Organization Name <span class="text-red-500">*</span>
								</label>
								<input
									type="text"
									id="organization"
									name="organization"
									required
									class="w-full rounded-lg border border-gray-300 px-3 py-2 text-sm focus:border-purple-500 focus:ring-2 focus:ring-purple-200 focus:outline-none sm:px-4 sm:text-base"
									placeholder="Enter company name"
								/>
							</div>
							<div>
								<label
									for="primary-contact"
									class="mb-2 block text-xs font-medium text-gray-700 sm:text-sm"
								>
									Primary Contact (Name and Title) <span class="text-red-500">*</span>
								</label>
								<input
									type="text"
									id="primary-contact"
									name="primary-contact"
									required
									class="w-full rounded-lg border border-gray-300 px-3 py-2 text-sm focus:border-purple-500 focus:ring-2 focus:ring-purple-200 focus:outline-none sm:px-4 sm:text-base"
									placeholder="e.g., John Doe, IT Manager"
								/>
							</div>
							<div>
								<label
									for="physical-address"
									class="mb-2 block text-xs font-medium text-gray-700 sm:text-sm"
								>
									Physical Address <span class="text-red-500">*</span>
								</label>
								<textarea
									id="physical-address"
									name="physical-address"
									rows="2"
									required
									class="w-full rounded-lg border border-gray-300 px-3 py-2 text-sm focus:border-purple-500 focus:ring-2 focus:ring-purple-200 focus:outline-none sm:px-4 sm:text-base"
									placeholder="Enter complete physical address"
								></textarea>
							</div>
							<div class="grid grid-cols-1 gap-4 sm:grid-cols-2">
								<div>
									<label
										for="email"
										class="mb-2 block text-xs font-medium text-gray-700 sm:text-sm"
									>
										Email Address <span class="text-red-500">*</span>
									</label>
									<input
										type="email"
										id="email"
										name="email"
										required
										class="w-full rounded-lg border border-gray-300 px-3 py-2 text-sm focus:border-purple-500 focus:ring-2 focus:ring-purple-200 focus:outline-none sm:px-4 sm:text-base"
										placeholder="your.email@organization.com"
									/>
								</div>
								<div>
									<label
										for="phone"
										class="mb-2 block text-xs font-medium text-gray-700 sm:text-sm"
									>
										Phone Number <span class="text-red-500">*</span>
									</label>
									<input
										type="tel"
										id="phone"
										name="phone"
										required
										class="w-full rounded-lg border border-gray-300 px-3 py-2 text-sm focus:border-purple-500 focus:ring-2 focus:ring-purple-200 focus:outline-none sm:px-4 sm:text-base"
										placeholder="+XXX XXX XXX XXX"
									/>
								</div>
							</div>
						</div>
					</div>

					<!-- Hardware & System Identifiers Section -->
					<div class="rounded-lg border-2 border-purple-200 bg-purple-50 p-4 sm:p-6">
						<h4 class="mb-3 text-base font-semibold text-purple-900 sm:mb-4 sm:text-lg">
							Hardware & System Identifiers
						</h4>
						<p class="mb-4 text-xs text-purple-700 sm:text-sm">
							<strong>Important:</strong> The following values must be retrieved from the Tasmal X System
							Information or Product Activation screen on the client's local machine.
						</p>
						<div class="space-y-4">
							<div class="grid grid-cols-1 gap-4 sm:grid-cols-2">
								<div>
									<label
										for="serial-number"
										class="mb-2 block text-xs font-medium text-gray-700 sm:text-sm"
									>
										Motherboard Serial Number (Serial No) <span class="text-red-500">*</span>
									</label>
									<input
										type="text"
										id="serial-number"
										name="serial-number"
										required
										class="w-full rounded-lg border border-gray-300 px-3 py-2 font-mono text-xs focus:border-purple-500 focus:ring-2 focus:ring-purple-200 focus:outline-none sm:px-4 sm:text-sm"
										placeholder="Enter Serial Number"
									/>
								</div>
								<div>
									<label
										for="hardware-id"
										class="mb-2 block text-xs font-medium text-gray-700 sm:text-sm"
									>
										Processor / Machine ID (Hardware Id) <span class="text-red-500">*</span>
									</label>
									<input
										type="text"
										id="hardware-id"
										name="hardware-id"
										required
										class="w-full rounded-lg border border-gray-300 px-3 py-2 font-mono text-xs focus:border-purple-500 focus:ring-2 focus:ring-purple-200 focus:outline-none sm:px-4 sm:text-sm"
										placeholder="Enter Hardware ID"
									/>
								</div>
							</div>
							<div class="grid grid-cols-1 gap-4 sm:grid-cols-2">
								<div>
									<label
										for="operating-system"
										class="mb-2 block text-xs font-medium text-gray-700 sm:text-sm"
									>
										Operating System <span class="text-red-500">*</span>
									</label>
									<select
										id="operating-system"
										name="operating-system"
										required
										class="w-full rounded-lg border border-gray-300 px-3 py-2 text-sm focus:border-purple-500 focus:ring-2 focus:ring-purple-200 focus:outline-none sm:px-4 sm:text-base"
									>
										<option value="">Select Operating System</option>
										<option value="Windows 10 Pro">Windows 10 Pro</option>
										<option value="Windows 11 Pro">Windows 11 Pro</option>
										<option value="Windows 10">Windows 10</option>
										<option value="Windows 11">Windows 11</option>
										<option value="Other">Other</option>
									</select>
								</div>
								<div>
									<label
										for="installation-site"
										class="mb-2 block text-xs font-medium text-gray-700 sm:text-sm"
									>
										Installation Site / Branch <span class="text-red-500">*</span>
									</label>
									<input
										type="text"
										id="installation-site"
										name="installation-site"
										required
										class="w-full rounded-lg border border-gray-300 px-3 py-2 text-sm focus:border-purple-500 focus:ring-2 focus:ring-purple-200 focus:outline-none sm:px-4 sm:text-base"
										placeholder="Enter branch or location"
									/>
								</div>
							</div>
						</div>
					</div>

					<!-- Current License Details & Renewal Specifications -->
					<div class="rounded-lg border-2 border-green-200 bg-green-50 p-4 sm:p-6">
						<h4 class="mb-4 text-base font-semibold text-green-900 sm:text-lg">
							Current License Details & Renewal Specifications
						</h4>
						<div class="space-y-4">
							<div>
								<label
									for="license-term"
									class="mb-2 block text-xs font-medium text-gray-700 sm:text-sm"
								>
									Requested License Term <span class="text-red-500">*</span>
								</label>
								<select
									id="license-term"
									name="license-term"
									required
									class="w-full rounded-lg border border-gray-300 px-3 py-2 text-sm focus:border-purple-500 focus:ring-2 focus:ring-purple-200 focus:outline-none sm:px-4 sm:text-base"
								>
									<option value="">Select license term</option>
									<option value="7d">7 days</option>
									<option value="1">1 year</option>
									<option value="2">2 years</option>
									<option value="3">3 years</option>
									<option value="5">5 years</option>
								</select>
							</div>
							<div>
								<label
									for="current-license"
									class="mb-2 block text-xs font-medium text-gray-700 sm:text-sm"
								>
									Current Activation Key (if available)
								</label>
								<input
									type="text"
									id="current-license"
									name="current-license"
									class="w-full rounded-lg border border-gray-300 px-3 py-2 font-mono text-xs focus:border-purple-500 focus:ring-2 focus:ring-purple-200 focus:outline-none sm:px-4 sm:text-sm"
									placeholder="Enter current activation key (optional)"
								/>
							</div>
							<div class="grid grid-cols-1 gap-4 sm:grid-cols-2">
								<div>
									<label
										for="current-license-start-date"
										class="mb-2 block text-xs font-medium text-gray-700 sm:text-sm"
									>
										Current License Start Date
									</label>
									<input
										type="date"
										id="current-license-start-date"
										name="current-license-start-date"
										class="w-full rounded-lg border border-gray-300 px-3 py-2 text-sm focus:border-purple-500 focus:ring-2 focus:ring-purple-200 focus:outline-none sm:px-4 sm:text-base"
									/>
								</div>
								<div>
									<label
										for="current-license-expiration-date"
										class="mb-2 block text-xs font-medium text-gray-700 sm:text-sm"
									>
										Current License Expiration Date
									</label>
									<input
										type="date"
										id="current-license-expiration-date"
										name="current-license-expiration-date"
										class="w-full rounded-lg border border-gray-300 px-3 py-2 text-sm focus:border-purple-500 focus:ring-2 focus:ring-purple-200 focus:outline-none sm:px-4 sm:text-base"
									/>
								</div>
							</div>
						</div>
					</div>

					<!-- Additional Notes -->
					<div>
						<label
							for="additional-notes"
							class="mb-2 block text-xs font-medium text-gray-700 sm:text-sm"
						>
							Additional Notes or Special Requirements
						</label>
						<textarea
							id="additional-notes"
							name="additional-notes"
							rows="4"
							class="w-full rounded-lg border border-gray-300 px-3 py-2 text-sm focus:border-purple-500 focus:ring-2 focus:ring-purple-200 focus:outline-none sm:px-4 sm:text-base"
							placeholder="Any additional information or special requirements..."
						></textarea>
					</div>

					<!-- Security Notice -->
					<div class="rounded-lg border-l-4 border-purple-500 bg-purple-50 p-4 sm:p-6">
						<div class="flex items-start">
							<ShieldIcon class="mt-0.5 mr-3 h-5 w-5 flex-shrink-0 text-purple-600" />
							<div class="min-w-0 flex-1">
								<p class="text-xs text-purple-700 sm:text-sm">
									<strong>Security Notice:</strong> All license renewals are processed securely. Your
									hardware identifiers are used exclusively for license binding and will not be shared
									with third parties. This ensures that your MICR Cheque Encoder license is tied to the
									specific machine intended for cheque production.
								</p>
							</div>
						</div>
					</div>

					<!-- Submit Button -->
					<div class="flex flex-col gap-4 sm:flex-row">
						<button
							type="submit"
							disabled={formSubmitting}
							class="w-full rounded bg-purple-600 px-6 py-3 text-sm font-semibold text-white transition hover:bg-purple-700 focus:ring-2 focus:ring-purple-500 focus:ring-offset-2 focus:outline-none disabled:cursor-not-allowed disabled:opacity-50 sm:w-auto sm:px-8"
						>
							{#if formSubmitting}
								<span class="flex items-center justify-center">
									<svg
										class="mr-2 h-4 w-4 animate-spin"
										xmlns="http://www.w3.org/2000/svg"
										fill="none"
										viewBox="0 0 24 24"
									>
										<circle
											class="opacity-25"
											cx="12"
											cy="12"
											r="10"
											stroke="currentColor"
											stroke-width="4"
										></circle>
										<path
											class="opacity-75"
											fill="currentColor"
											d="M4 12a8 8 0 018-8V0C5.373 0 0 5.373 0 12h4zm2 5.291A7.962 7.962 0 014 12H0c0 3.042 1.135 5.824 3 7.938l3-2.647z"
										></path>
									</svg>
									Submitting...
								</span>
							{:else}
								Submit Renewal Request
							{/if}
						</button>
						<button
							type="reset"
							disabled={formSubmitting}
							class="w-full rounded border border-gray-300 bg-white px-6 py-3 text-sm font-semibold text-gray-700 transition hover:bg-gray-50 focus:ring-2 focus:ring-gray-500 focus:ring-offset-2 focus:outline-none disabled:cursor-not-allowed disabled:opacity-50 sm:w-auto sm:px-8"
						>
							Clear Form
						</button>
					</div>
				</form>
			{/if}
		</div>

		<!-- Support Contact -->
		<div class="rounded-lg bg-gray-100 p-4 sm:p-6">
			<h3 class="mb-3 text-base font-semibold sm:text-lg">Need Assistance?</h3>
			<p class="mb-4 text-sm text-gray-700 sm:text-base">
				If you encounter any issues during the renewal process or have questions about your license,
				please contact our support team:
			</p>
			<div class="flex flex-col gap-4 sm:flex-row sm:flex-wrap">
				<a
					href="mailto:service.engineer@olujohnsonbusinesstechnicalservices.com"
					class="inline-flex w-full items-center justify-center rounded bg-purple-600 px-4 py-2 text-sm text-white transition hover:bg-purple-700 sm:w-auto"
				>
					Email Support
				</a>
				<a
					href="tel:+23278220326"
					class="inline-flex w-full items-center justify-center rounded border border-purple-600 bg-white px-4 py-2 text-sm text-purple-600 transition hover:bg-purple-50 sm:w-auto"
				>
					Call: +232 782 20326
				</a>
			</div>
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
				href="mailto:service.engineer@olujohnsonbusinesstechnicalservices.com"
				class="rounded bg-purple-600 px-6 py-3 font-bold text-white transition hover:bg-purple-700"
				>Request Demo</a
			>
			<a
				href="tel:+23278220326"
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
