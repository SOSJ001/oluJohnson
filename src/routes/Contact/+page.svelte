<script>
	import BreadCrumb from '$lib/components/BreadCrumb.svelte';
	import Footer from '$lib/components/Footer.svelte';
</script>

<BreadCrumb />
<!-- Hero Section -->

<main class="container mx-auto px-4 py-8">
<section
	style="background-image: url('/purple-Bg.jpg');"
	class="relative mb-5 rounded-lg bg-gray-800 bg-cover bg-no-repeat px-3 py-6 text-gray-200 md:px-10 md:py-20"
>
	<div class="animate-fade-in container mx-auto px-4 text-center">
		<div class="mb-4 flex flex-col items-center justify-center">
			<h1 class="mb-2 text-4xl font-bold md:text-5xl">Contact Us</h1>
			<p class="mx-auto mb-2 max-w-2xl text-lg md:text-xl">
				We're here to help. Reach out for quotes, support, or partnership inquiries.
			</p>
		</div>
	</div>
</section>
	<div class="mb-12 grid grid-cols-1 gap-8 md:grid-cols-2">
		<!-- Contact Info Card -->
		<div
			class="flex flex-col items-start rounded-2xl border border-gray-100 bg-white p-8 shadow-lg transition-shadow hover:shadow-xl"
		>
			<div
				class="mb-4 flex h-12 w-12 items-center justify-center rounded-full bg-purple-100 text-purple-600"
			>
				<svg
					xmlns="http://www.w3.org/2000/svg"
					class="h-6 w-6"
					fill="none"
					viewBox="0 0 24 24"
					stroke="currentColor"
					><path
						stroke-linecap="round"
						stroke-linejoin="round"
						stroke-width="2"
						d="M16 12A4 4 0 118 12a4 4 0 018 0zM12 14v7m0 0H9m3 0h3"
					/></svg
				>
			</div>
			<div class="mb-2 text-lg font-semibold">Contact Info</div>
			<div class="mb-2 text-sm text-gray-600">
				<span class="block"
					>Email: <a href="mailto:info@tasmal.com" class="underline hover:text-purple-700"
						>info@tasmal.com</a
					></span
				>
				<span class="block"
					>Phone: <a href="tel:+233555132456" class="underline hover:text-purple-700"
						>+233 555 132 456</a
					></span
				>
				<span class="block">Location: Accra, Ghana</span>
				<span class="block">Service Area: West Africa & International</span>
			</div>
			<div class="mt-3 flex gap-2">
				<a
					href="mailto:info@tasmal.com"
					class="rounded bg-purple-600 px-4 py-2 text-sm font-semibold text-white transition hover:bg-purple-700"
					>Email Us</a
				>
				<a
					href="tel:+233555132456"
					class="rounded bg-purple-100 px-4 py-2 text-sm font-semibold text-purple-700 transition hover:bg-purple-200"
					>Call Now</a
				>
			</div>
		</div>
		<!-- Book Online Card -->
		<div
			class="flex flex-col items-start rounded-2xl border border-gray-100 bg-white p-8 shadow-lg transition-shadow hover:shadow-xl"
		>
			<div
				class="mb-4 flex h-12 w-12 items-center justify-center rounded-full bg-purple-100 text-purple-600"
			>
				<svg
					xmlns="http://www.w3.org/2000/svg"
					class="h-6 w-6"
					fill="none"
					viewBox="0 0 24 24"
					stroke="currentColor"
					><path
						stroke-linecap="round"
						stroke-linejoin="round"
						stroke-width="2"
						d="M8 7V3m8 4V3m-9 8h10M5 21h14a2 2 0 002-2V7a2 2 0 00-2-2H5a2 2 0 00-2 2v12a2 2 0 002 2z"
					/></svg
				>
			</div>
			<div class="mb-2 text-lg font-semibold">Book Online</div>
			<div class="mb-4 text-sm text-gray-600">
				Schedule a repair or software consultation at your convenience.
			</div>
			<a
				href="#"
				class="rounded bg-purple-600 px-4 py-2 text-sm font-semibold text-white transition hover:bg-purple-700"
				>Book Appointment</a
			>
		</div>
	</div>

	<div class="my-8 flex items-center">
		<div class="flex-grow border-t border-gray-200"></div>
		<span class="mx-4 font-semibold text-gray-400">OR</span>
		<div class="flex-grow border-t border-gray-200"></div>
	</div>

	<form class="mx-auto max-w-2xl rounded-2xl border border-gray-100 bg-white p-8 shadow-lg">
		<h2 class="mb-6 text-center text-2xl font-bold">Send a Message</h2>
		<div class="mb-4 grid grid-cols-1 gap-6 md:grid-cols-2">
			<div>
				<label class="mb-1 block font-semibold" for="name">Name</label>
				<input
					id="name"
					name="name"
					type="text"
					placeholder="Your full name"
					class="w-full rounded border border-gray-200 bg-gray-50 px-4 py-3 focus:ring-2 focus:ring-purple-200 focus:outline-none"
					required
				/>
			</div>
			<div>
				<label class="mb-1 block font-semibold" for="email">Email</label>
				<div class="relative">
					<input
						id="email"
						name="email"
						type="email"
						placeholder="you@email.com"
						class="w-full rounded border border-gray-200 bg-gray-50 px-4 py-3 pr-10 focus:ring-2 focus:ring-purple-200 focus:outline-none"
						required
					/>
					<span class="absolute top-1/2 right-3 -translate-y-1/2 transform text-gray-400">
						<svg
							xmlns="http://www.w3.org/2000/svg"
							class="h-5 w-5"
							fill="none"
							viewBox="0 0 24 24"
							stroke="currentColor"
							><path
								stroke-linecap="round"
								stroke-linejoin="round"
								stroke-width="2"
								d="M16 12A4 4 0 118 12a4 4 0 018 0zM12 14v7m0 0H9m3 0h3"
							/></svg
						>
					</span>
				</div>
			</div>
		</div>
		<div class="mb-4">
			<label class="mb-1 block font-semibold" for="message">Message</label>
			<textarea
				id="message"
				name="message"
				rows="4"
				placeholder="How can we help you?"
				class="w-full rounded border border-gray-200 bg-gray-50 px-4 py-3 focus:ring-2 focus:ring-purple-200 focus:outline-none"
				required
			></textarea>
		</div>
		<button
			type="submit"
			class="w-full rounded bg-purple-600 px-6 py-3 text-lg font-semibold text-white transition hover:bg-purple-700"
			>Send Message</button
		>
		<p class="mt-4 text-center text-xs text-gray-500">Our team responds within 1 business day.</p>
	</form>
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
