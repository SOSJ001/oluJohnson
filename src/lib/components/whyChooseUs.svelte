<script>
	import { GlobeIcon, LockIcon, ThumbsUpIcon } from 'svelte-feather-icons';
</script>

<!-- Why Choose Us -->
<div class="container mx-auto pb-4 px-4">
	<h2 class="mb-4 text-2xl font-bold">Why Choose Us</h2>
	<div class="grid grid-cols-1 gap-8 md:grid-cols-3">
		<!-- Trusted Experts -->
		<div
			class="transform rounded-lg bg-white p-6 shadow-md transition duration-300 hover:scale-105"
		>
			<div class="mb-4 flex items-center justify-start text-gray-100">
				<span class="rounded-full bg-purple-600 p-1"><ThumbsUpIcon /></span>
			</div>
			<h2 class="mb-2 text-xl font-bold">Trusted Experts</h2>
			<p class="mb-4">Decades of experience in hardware and software.</p>
		</div>

		<!-- Global Reach -->
		<div
			class="transform rounded-lg bg-white p-6 shadow-md transition duration-300 hover:scale-105"
		>
        <div class="mb-4 flex items-center justify-start text-gray-100">
            <span class="rounded-full bg-purple-600 p-1"><GlobeIcon /></span>
        </div>
			<h2 class="mb-2 text-xl font-bold">Global Reach</h2>
			<p class="mb-4">Serving clients across West Africa and beyond.</p>
		</div>

		<!-- Secure Solutions -->
		<div
			class="transform rounded-lg bg-white p-6 shadow-md transition duration-300 hover:scale-105"
		>
        <div class="mb-4 flex items-center justify-start text-gray-100">
            <span class="rounded-full bg-purple-600 p-1"><LockIcon /></span>
        </div>
			<h2 class="mb-2 text-xl font-bold">Secure Solutions</h2>
			<p class="mb-4">Compliance and security at every step.</p>
		</div>
	</div>
</div>
