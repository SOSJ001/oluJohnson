<script>
	let mobileOpen = false;
</script>

<nav class="relative flex flex-wrap items-center justify-between bg-gray-100 p-6 shadow-md">
	<div class="text-xl font-semibold tracking-tight text-purple-700">Olu Johnson</div>
	<div class="block lg:hidden">
		<!-- svelte-ignore a11y_consider_explicit_label -->
		<button
			class="text-gray-500 hover:text-purple-700 focus:outline-none"
			on:click={() => (mobileOpen = !mobileOpen)}
			aria-label="Toggle navigation"
		>
			<svg
				xmlns="http://www.w3.org/2000/svg"
				class="h-8 w-8"
				fill="none"
				viewBox="0 0 24 24"
				stroke="currentColor"
				><path
					stroke-linecap="round"
					stroke-linejoin="round"
					stroke-width="2"
					d="M4 6h16M4 12h16M4 18h16"
				/></svg
			>
		</button>
	</div>
	<div class="hidden w-full lg:flex lg:w-auto lg:items-center">
		<div class="text-sm lg:flex-grow">
			<a
				href="/"
				class="mt-4 mr-6 block text-gray-700 hover:text-purple-700 lg:mt-0 lg:inline-block"
			>
				<i class="fas fa-home mr-1"></i> Home
			</a>
			<a
				href="/Services"
				class="mt-4 mr-6 block text-gray-700 hover:text-purple-700 lg:mt-0 lg:inline-block"
			>
				<i class="fas fa-wrench mr-1"></i> Services
			</a>
			<a
				href="/Tasmal-X"
				class="mt-4 mr-6 block text-gray-700 hover:text-purple-700 lg:mt-0 lg:inline-block"
			>
				<i class="fas fa-shield-alt mr-1"></i> Tasmal-X
			</a>
			<a
				href="Industries"
				class="mt-4 mr-6 block text-gray-700 hover:text-purple-700 lg:mt-0 lg:inline-block"
			>
				<i class="fas fa-industry mr-1"></i> Industries
			</a>
			<a
				href="/Brands"
				class="mt-4 mr-6 block text-gray-700 hover:text-purple-700 lg:mt-0 lg:inline-block"
			>
				<i class="fas fa-cubes mr-1"></i> Brands
			</a>
			<a
				href="/About"
				class="mt-4 mr-6 block text-gray-700 hover:text-purple-700 lg:mt-0 lg:inline-block"
			>
				<i class="fas fa-info-circle mr-1"></i> About
			</a>
			<a
				href="/Contact"
				class="mt-4 mr-6 block text-gray-700 hover:text-purple-700 lg:mt-0 lg:inline-block"
			>
				<i class="fas fa-envelope mr-1"></i> Contact
			</a>
		</div>
		<div class="flex space-x-4">
			<a
				href="#"
				class="inline-block rounded border bg-purple-600 px-4 py-2 text-sm text-white transition hover:bg-purple-700"
				>Book Online</a
			>
			<a
				href="#"
				class="inline-block rounded border border-purple-600 px-4 py-2 text-sm text-purple-600 transition hover:bg-purple-100"
				>Get a Quote</a
			>
		</div>
	</div>
	{#if mobileOpen}
		<div
			class="animate-fade-in absolute top-full left-0 z-50 flex w-full flex-col bg-gray-100 p-6 shadow-lg lg:hidden"
		>
			<a
				href="/"
				class="mb-4 text-gray-700 hover:text-purple-700"
				on:click={() => (mobileOpen = false)}><i class="fas fa-home mr-1"></i> Home</a
			>
			<a
				href="/Services"
				class="mb-4 text-gray-700 hover:text-purple-700"
				on:click={() => (mobileOpen = false)}><i class="fas fa-wrench mr-1"></i> Services</a
			>
			<a
				href="/Tasmal-X"
				class="mb-4 text-gray-700 hover:text-purple-700"
				on:click={() => (mobileOpen = false)}><i class="fas fa-shield-alt mr-1"></i> Tasmal-X</a
			>
			<a
				href="Industries"
				class="mb-4 text-gray-700 hover:text-purple-700"
				on:click={() => (mobileOpen = false)}><i class="fas fa-industry mr-1"></i> Industries</a
			>
			<a
				href="/Brands"
				class="mb-4 text-gray-700 hover:text-purple-700"
				on:click={() => (mobileOpen = false)}><i class="fas fa-cubes mr-1"></i> Brands</a
			>
			<a
				href="/About"
				class="mb-4 text-gray-700 hover:text-purple-700"
				on:click={() => (mobileOpen = false)}><i class="fas fa-info-circle mr-1"></i> About</a
			>
			<a
				href="/Contact"
				class="mb-4 text-gray-700 hover:text-purple-700"
				on:click={() => (mobileOpen = false)}><i class="fas fa-envelope mr-1"></i> Contact</a
			>
			<div class="mt-4 flex flex-col space-y-2">
				<a
					href="#"
					class="inline-block rounded border bg-purple-600 px-4 py-2 text-sm text-white transition hover:bg-purple-700"
					>Book Online</a
				>
				<a
					href="#"
					class="inline-block rounded border border-purple-600 px-4 py-2 text-sm text-purple-600 transition hover:bg-purple-100"
					>Get a Quote</a
				>
			</div>
		</div>
	{/if}
</nav>

<style>
	@keyframes fade-in {
		from {
			opacity: 0;
			transform: translateY(-10px);
		}
		to {
			opacity: 1;
			transform: translateY(0);
		}
	}
	.animate-fade-in {
		animation: fade-in 0.2s ease-out;
	}
</style>
