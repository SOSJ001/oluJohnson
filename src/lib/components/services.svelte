<script>
	import { CodeIcon, ShieldIcon, ToolIcon } from "svelte-feather-icons";

</script>
<section class="py-10 bg-gray-50">
  <div class="container mx-auto px-4 grid grid-cols-1 md:grid-cols-3 gap-8">
    <!-- Hardware Repair -->
    <div class="bg-white rounded-lg shadow-md p-6 transform hover:scale-105 transition duration-300">
      <div class="flex items-center justify-start mb-4 text-gray-100">
        <span class="rounded-full bg-purple-600 p-1"><ToolIcon /></span>
      </div>
      <h2 class="text-2xl font-bold mb-2">Hardware Repair</h2>
      <p class="mb-4">Certified repairs for printers, scanners, cheque encoders, and more. Fast turnaround, genuine parts.</p>
      <a href="/#" class="bg-purple-600 hover:bg-purple-700 text-white font-bold py-2 px-4 rounded transition">Request Quote</a>
    </div>

    <!-- Software Solutions -->
    <div class="bg-white rounded-lg shadow-md p-6 transform hover:scale-105 transition duration-300">
      <div class="flex items-center justify-start mb-4 text-gray-100">
        <span class="rounded-full bg-purple-600 p-1"><CodeIcon /></span>
      </div>
      <h2 class="text-2xl font-bold mb-2">Software Solutions</h2>
      <p class="mb-4">Custom business software, automation, and integration. Secure, scalable, and tailored to your needs.</p>
      <a href="/#" class="bg-purple-600 hover:bg-purple-700 text-white font-bold py-2 px-4 rounded transition">See Solutions</a>
    </div>

    <!-- Flagship Product -->
    <div class="bg-white rounded-lg shadow-md p-6 transform hover:scale-105 transition duration-300">
      <div class="flex items-center justify-start mb-4 text-gray-100">
        <span class="rounded-full bg-purple-600 p-1"><ShieldIcon /></span>
      </div>
      <h2 class="text-2xl font-bold mb-2">Flagship Product</h2>
      <h3 class="text-xl font-bold mb-2">Tasmal x Cheque Encoder</h3>
      <p class="mb-4">Industry-leading cheque encoding software. Advanced security, seamless integration, global compliance.</p>
      <a href="/#" class="bg-purple-600 hover:bg-purple-700 text-white font-bold py-2 px-4 rounded transition">Explore Tasmal x</a>
    </div>
  </div>
</section>