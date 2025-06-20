<div class="bg-gray-800 py-12">
    <div class="container mx-auto px-4">
      <p class="text-center text-gray-400 mb-6">Brands We Repair</p>
      <div class="grid grid-cols-2 sm:grid-cols-3 md:grid-cols-5 gap-6 text-center">
        {#each ["HP", "Canon", "Epson", "Brother", "Lexmark", "Zebra", "Ricoh", "Xerox", "Konica Minolta", "Sharp", "Fargo", "Evolis"] as brand}
          <div class="py-4 px-2 bg-gray-900 rounded shadow">{brand}</div>
        {/each}
      </div>
    </div>
  </div>