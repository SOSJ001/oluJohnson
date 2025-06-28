<script>
	import BreadCrumb from "$lib/components/BreadCrumb.svelte";
	import Footer from "$lib/components/Footer.svelte";

</script>
 <BreadCrumb/>
 <!-- Main Content -->
 <main class="container mx-auto px-4">

    <!-- Header -->
    <section style="background-image: url('/purple-Bg.jpg');" class="bg-cover bg-no-repeat relative mb-5 rounded-lg bg-gray-800 text-gray-200 py-6 px-3 md:px-10 md:py-20">
      <h1 class="text-4xl md:text-5xl font-bold mb-6">Brands We Service</h1>
      <p class="text-lg">
        We expertly repair and support a wide range of leading hardware brands for offices, banks, and institutions.</p> 
        <p>Our certified technicians use genuine parts and proven processes to ensure reliability and performance.</p>
    </section>

    <!-- Major Brands Section -->
    <section class="mb-10">
      <h2 class="text-2xl font-bold mb-6">Major Brands</h2>
      <div class="grid grid-cols-1 md:grid-cols-3 gap-6">
        <!-- HP -->
        <div class="bg-white rounded-lg shadow-md p-6 transform hover:scale-105 transition duration-300">
          <div class="flex items-center justify-center mb-4 text-purple-500">
            <i class="fas fa-print text-4xl"><img src="/HP-Logo.png" class="h-[36px]" alt=""></i>
          </div>
          <h3 class="text-xl font-bold mb-2">HP</h3>
          <p class="mb-4">Printers, Scanners, Cheque Encoders</p>
        </div>

        <!-- Canon -->
        <div class="bg-white rounded-lg shadow-md p-6 transform hover:scale-105 transition duration-300">
          <div class="flex items-center justify-center mb-4 text-purple-500">
            <i class="fas fa-camera text-4xl"></i>
          </div>
          <h3 class="text-xl font-bold mb-2">Canon</h3>
          <p class="mb-4">Printers, Scanners</p>
        </div>

        <!-- Epson -->
        <div class="bg-white rounded-lg shadow-md p-6 transform hover:scale-105 transition duration-300">
          <div class="flex items-center justify-center mb-4 text-purple-500">
            <i class="fas fa-check-square text-4xl"></i>
          </div>
          <h3 class="text-xl font-bold mb-2">Epson</h3>
          <p class="mb-4">Cheque Encoders, Printers</p>
        </div>

        <!-- Dell -->
        <div class="bg-white rounded-lg shadow-md p-6 transform hover:scale-105 transition duration-300">
          <div class="flex items-center justify-center mb-4 text-purple-500">
            <i class="fas fa-desktop text-4xl"></i>
          </div>
          <h3 class="text-xl font-bold mb-2">Dell</h3>
          <p class="mb-4">Workstations, Laptops</p>
        </div>

        <!-- Lenovo -->
        <div class="bg-white rounded-lg shadow-md p-6 transform hover:scale-105 transition duration-300">
          <div class="flex items-center justify-center mb-4 text-purple-500">
            <i class="fas fa-laptop text-4xl"></i>
          </div>
          <h3 class="text-xl font-bold mb-2">Lenovo</h3>
          <p class="mb-4">Laptops, Desktops</p>
        </div>

        <!-- Fujitsu -->
        <div class="bg-white rounded-lg shadow-md p-6 transform hover:scale-105 transition duration-300">
          <div class="flex items-center justify-center mb-4 text-purple-500">
            <i class="fas fa-file-contract text-4xl"></i>
          </div>
          <h3 class="text-xl font-bold mb-2">Fujitsu</h3>
          <p class="mb-4">Scanners, Cheque Encoders</p>
        </div>

        <!-- Panasonic -->
        <div class="bg-white rounded-lg shadow-md p-6 transform hover:scale-105 transition duration-300">
          <div class="flex items-center justify-center mb-4 text-purple-500">
            <i class="fas fa-cogs text-4xl"></i>
          </div>
          <h3 class="text-xl font-bold mb-2">Panasonic</h3>
          <p class="mb-4">Scanners, Printers</p>
        </div>

        <!-- Magner -->
        <div class="bg-white rounded-lg shadow-md p-6 transform hover:scale-105 transition duration-300">
          <div class="flex items-center justify-center mb-4 text-purple-500">
            <i class="fas fa-balance-scale text-4xl"></i>
          </div>
          <h3 class="text-xl font-bold mb-2">Magner</h3>
          <p class="mb-4">Cheque Encoders</p>
        </div>

        <!-- Glory -->
        <div class="bg-white rounded-lg shadow-md p-6 transform hover:scale-105 transition duration-300">
          <div class="flex items-center justify-center mb-4 text-purple-500">
            <i class="fas fa-money-bill-wave text-4xl"></i>
          </div>
          <h3 class="text-xl font-bold mb-2">Glory</h3>
          <p class="mb-4">Banking Equipment</p>
        </div>
      </div>
    </section>

    <!-- Call-to-Action -->
    <section class="mb-10">
      <p class="text-lg mb-6">
        Don’t see your brand? Contact us for support with additional manufacturers.
      </p>
      <a href="#" class="bg-purple-600 hover:bg-purple-700 text-white font-bold py-3 px-6 rounded transition">Request Brand Support</a>
    </section>

  </main>
  <Footer/>