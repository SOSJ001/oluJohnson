<script>
	import BreadCrumb from "./BreadCrumb.svelte";

</script>
<section class="py-10 md:flex grid items-center justify-center">
  <div class="container mx-auto px-4 text-center animate-fade-in">
    <h1 class="text-4xl md:text-5xl font-bold mb-6 text-gray-700 drop-shadow-lg">Expert Hardware Repair & Custom Software</h1>
    <p class="text-xl text-gray-700 mb-8 max-w-3xl mx-auto drop-shadow-md">
      Trusted by offices, banks, and institutions worldwide. Based in West Africa, delivering reliable repairs and innovative software solutions.
    </p>
    <div class="flex flex-wrap justify-center gap-4">
      <a href="#" class="bg-purple-600 hover:bg-purple-700 text-white font-bold py-3 px-6 rounded transition">Get a Repair Quote</a> 
      <a href="#" class="bg-white hover:bg-gray-100 text-purple-800 font-bold py-3 px-6 rounded shadow transition">Book Service Online</a>
      <a href="#" class="bg-purple-100 hover:bg-purple-200 text-purple-800 font-bold py-3 px-6 rounded transition">Learn About Tasmal x</a>
    </div>
  </div>
  <div class="md:w-2/3 flex justify-center items-center animate-fade-out">
    <img src="/fix.png" alt="fix" class="h-auto">
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

	@keyframes fadeOut {
		from {
			opacity: 0;
			transform: translateY(-20px);
		}
		to {
			opacity: 1;
			transform: translateY(0);
		}
	}

	.animate-fade-out {
		animation: fadeOut 1s ease-out forwards;
	}
</style>