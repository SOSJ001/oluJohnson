<script>
	import TrustedCompanies from './TrustedCompanies.svelte';
	import { AwardIcon, UsersIcon, GlobeIcon, ShieldIcon } from 'svelte-feather-icons';
</script>

<!-- Hero Section -->
<section
	style="background-image: url('/purple-Bg.jpg');"
	class="rounded-lg bg-gradient-to-br from-purple-600 via-purple-700 to-purple-800 bg-no-repeat py-16 text-white"
>
	<div class="animate-fade-in container mx-auto px-4 text-center">
		<h1 class="mb-6 text-4xl font-bold md:text-6xl">About Olu Johnson</h1>
		<p class="mx-auto max-w-3xl text-xl opacity-90 md:text-2xl">
			Empowering businesses across West Africa with innovative technology solutions and reliable
			hardware support.
		</p>
	</div>
</section>

<!-- Stats Section -->
<section class="border-b bg-white py-12">
	<div class="container mx-auto px-4">
		<div class="grid grid-cols-2 gap-8 text-center md:grid-cols-4">
			<div class="p-6">
				<div class="mb-2 text-3xl font-bold text-purple-600 md:text-4xl">15+</div>
				<div class="text-gray-600">Years Experience</div>
			</div>
			<div class="p-6">
				<div class="mb-2 text-3xl font-bold text-purple-600 md:text-4xl">500+</div>
				<div class="text-gray-600">Happy Clients</div>
			</div>
			<div class="p-6">
				<div class="mb-2 text-3xl font-bold text-purple-600 md:text-4xl">1000+</div>
				<div class="text-gray-600">Projects Completed</div>
			</div>
			<div class="p-6">
				<div class="mb-2 text-3xl font-bold text-purple-600 md:text-4xl">24/7</div>
				<div class="text-gray-600">Support Available</div>
			</div>
		</div>
	</div>
</section>

<!-- Our Story Section -->
<section class="bg-gray-50 py-16">
	<div class="container mx-auto px-4">
		<div class="mx-auto max-w-4xl">
			<h2 class="mb-12 text-center text-3xl font-bold md:text-4xl">Our Story</h2>
			<div class="grid items-center gap-12 md:grid-cols-2">
				<div>
					<p class="mb-6 text-lg leading-relaxed text-gray-700">
						Founded in West Africa, Olu Johnson Business Technical Service was built on a passion
						for technology and a commitment to reliability. We serve offices, banks, and
						institutions worldwide, delivering expert hardware repair and innovative software
						tailored to your needs.
					</p>
					<p class="text-lg leading-relaxed text-gray-700">
						Our journey began with a simple mission: to bridge the gap between complex technology
						and practical business needs. Today, we're proud to be trusted partners for
						organizations across the region.
					</p>
				</div>
				<div class="relative">
					<img src="/fix.png" alt="Our Work" class="w-full rounded-lg shadow-xl" />
					<div class="absolute -right-4 -bottom-4 rounded-lg bg-purple-600 p-4 text-white">
						<AwardIcon class="h-8 w-8" />
					</div>
				</div>
			</div>
		</div>
	</div>
</section>

<!-- Mission & Values -->
<section class="bg-white py-16">
	<div class="container mx-auto px-4">
		<div class="mx-auto max-w-4xl">
			<h2 class="mb-12 text-center text-3xl font-bold md:text-4xl">Our Mission & Values</h2>
			<div class="grid gap-8 md:grid-cols-3">
				<div class="p-6 text-center">
					<div
						class="mx-auto mb-4 flex h-16 w-16 items-center justify-center rounded-full bg-purple-100"
					>
						<ShieldIcon class="h-8 w-8 text-purple-600" />
					</div>
					<h3 class="mb-3 text-xl font-semibold">Reliability</h3>
					<p class="text-gray-600">
						We deliver consistent, high-quality solutions that businesses can depend on.
					</p>
				</div>
				<div class="p-6 text-center">
					<div
						class="mx-auto mb-4 flex h-16 w-16 items-center justify-center rounded-full bg-purple-100"
					>
						<GlobeIcon class="h-8 w-8 text-purple-600" />
					</div>
					<h3 class="mb-3 text-xl font-semibold">Innovation</h3>
					<p class="text-gray-600">
						Constantly evolving our solutions to meet the changing needs of modern businesses.
					</p>
				</div>
				<div class="p-6 text-center">
					<div
						class="mx-auto mb-4 flex h-16 w-16 items-center justify-center rounded-full bg-purple-100"
					>
						<UsersIcon class="h-8 w-8 text-purple-600" />
					</div>
					<h3 class="mb-3 text-xl font-semibold">Partnership</h3>
					<p class="text-gray-600">
						Building long-term relationships based on trust, transparency, and mutual success.
					</p>
				</div>
			</div>
		</div>
	</div>
</section>

<!-- Founder Section -->
<section class="bg-gray-50 py-16">
	<div class="container mx-auto px-4">
		<div class="mx-auto max-w-4xl">
			<h2 class="mb-12 text-center text-3xl font-bold md:text-4xl">Meet Our Founder</h2>
			<div class="rounded-xl bg-white p-8 shadow-lg md:p-12">
				<div class="items-center gap-8 md:flex">
					<div class="mb-6 flex-shrink-0 md:mb-0">
						<img
							src="/Founder.jpeg"
							alt="Founder"
							class="h-48 w-48 rounded-full object-cover shadow-lg"
						/>
					</div>
					<div>
						<h3 class="mb-4 text-2xl font-bold">Olu Johnson</h3>
						<p class="mb-6 text-lg leading-relaxed text-gray-600">
							With decades of experience in hardware engineering and software development, our
							founder leads a team dedicated to quality, transparency, and client success. His
							vision drives our commitment to excellence.
						</p>
						<div class="grid grid-cols-2 gap-4 text-sm">
							<div class="rounded bg-purple-50 p-3">
								<div class="font-semibold text-purple-600">Hardware Expert</div>
								<div class="text-gray-600">25+ years experience</div>
							</div>
							<div class="rounded bg-purple-50 p-3">
								<div class="font-semibold text-purple-600">Software Expert</div>
								<div class="text-gray-600">6+ years experience</div>
							</div>
						</div>
					</div>
				</div>
			</div>
		</div>
	</div>
</section>

<!-- Team Section -->
<section class="bg-white py-16">
	<div class="container mx-auto px-4">
		<div class="mx-auto max-w-4xl">
			<h2 class="mb-12 text-center text-3xl font-bold md:text-4xl">Our Team</h2>
			<div class="grid gap-8 md:grid-cols-3">
				<div class="rounded-xl bg-gray-50 p-6 text-center transition-shadow hover:shadow-lg">
					<img
						src="/Founder.jpeg"
						alt="Olu Johnson"
						class="mx-auto mb-4 h-24 w-24 rounded-full object-cover shadow"
					/>
					<h3 class="mb-2 text-xl font-semibold">Olu Johnson</h3>
					<p class="mb-3 font-medium text-purple-600">Lead Engineer</p>
					<p class="text-sm text-gray-600">
						Expert in hardware diagnostics and repair with 25+ years of experience.
					</p>
				</div>
				<div class="rounded-xl bg-gray-50 p-6 text-center transition-shadow hover:shadow-lg">
					<img
						src="/SoftwareEngineer.jpeg"
						alt="Michael Johnson"
						class="mx-auto mb-4 h-24 w-24 rounded-full object-cover shadow"
					/>
					<h3 class="mb-2 text-xl font-semibold">Michael S.O.S Johnson</h3>
					<p class="mb-3 font-medium text-purple-600">Software Architect</p>
					<p class="text-sm text-gray-600">
						Specializes in custom software development and Cyber Security.
					</p>
				</div>
				<div class="rounded-xl bg-gray-50 p-6 text-center transition-shadow hover:shadow-lg">
					<img
						src="https://placehold.co/96x96"
						alt="Fatou Bayo"
						class="mx-auto mb-4 h-24 w-24 rounded-full object-cover shadow"
					/>
					<h3 class="mb-2 text-xl font-semibold">Sahr Fanday</h3>
					<p class="mb-3 font-medium text-purple-600">I.T Support</p>
					<p class="text-sm text-gray-600">
						Ensures exceptional customer experience and project delivery.
					</p>
				</div>
			</div>
		</div>
	</div>
</section>

<!-- Trusted By Section -->
<section class="bg-gray-50 py-16">
	<div class="container mx-auto px-4">
		<div class="mx-auto max-w-4xl">
			<h2 class="mb-12 text-center text-3xl font-bold md:text-4xl">
				Trusted By Leading Organizations
			</h2>
			<TrustedCompanies />
		</div>
	</div>
</section>

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
