<script>
	import { AirplayIcon, CastIcon } from 'svelte-feather-icons';

	let companies = [
		'/Bloomlogo.png',
		'/gtbank.png',
		'/zenith.png',
		'/uba.png',
		'vista.png',
		'/eco.png',
		'/limkokwingUni.png',
		'/vitaFoam.png'
	];
</script>

<section class="py-10">
	<div class="container mx-auto px-4">
		<h2 class="mb-8 text-2xl font-bold">Trusted By</h2>
		<div class="flex space-x-10 overflow-x-auto pb-4 md:items-center md:justify-center">
			{#each companies as i}
				<img
					loading="lazy"
					src={i}
					alt={`Logo ${i}`}
					class="h-32 w-32 flex-shrink-0 rounded object-contain shadow-sm"
				/>
			{/each}
		</div>
	</div>
</section>
