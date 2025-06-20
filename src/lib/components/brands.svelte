<section id="brands" class="py-16 bg-gray-800">
    <div class="container mx-auto px-4">
      <h2 class="text-3xl font-bold mb-6 text-center">Brands We Service</h2>
      <div class="grid grid-cols-2 sm:grid-cols-3 md:grid-cols-5 gap-4 text-center">
        {#each ["HP", "Canon", "Epson", "Brother", "Lexmark", "Zebra", "Ricoh", "Xerox", "Konica Minolta", "Sharp", "Fargo", "Evolis"] as brand}
          <div class="py-4 px-2 bg-gray-900 rounded shadow">{brand}</div>
        {/each}
      </div>
    </div>
  </section>