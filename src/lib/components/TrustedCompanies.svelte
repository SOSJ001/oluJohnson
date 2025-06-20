<script>
	let companies = ["/Bloomlogo.png", "/gtbank.png", "/zenith.png", "/limkokwingUni.png", "/vitaFoam.png"];
</script>

<section class="py-10">
	<div class="container mx-auto px-4">
		<h2 class="mb-8 text-2xl font-bold">Trusted By</h2>
		<div class="flex items-center justify-center space-x-10 overflow-x-auto pb-4">
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
