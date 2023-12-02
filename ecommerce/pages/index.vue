<template>
  <!-- component -->
  <div class="w-full h-full">
    <div class="flex bg-white" style="height: 600px;">
      <div class="flex items-center text-center lg:text-left px-8 md:px-12 lg:w-1/2">
        <div>
          <h2 class="text-3xl font-semibold text-gray-800 md:text-4xl">Selamat Datang di <br>
            <span class="text-secondary font-boldZ">Astra Store</span></h2>
          <p class="mt-2 text-sm text-gray-800 md:text-base">Astra Store adalah situs toko buku online yang menyediakan aneka buku berkualitas dan terlengkap, mulai dari buku-buku populer, e-book, pilihan, hingga buku-buku international lainya.</p>
          <div class="flex justify-center lg:justify-start mt-6">
            <a class="px-4 py-3 bg-primary text-white text-xs font-semibold rounded" href="#">Lihat Buku</a>
            <a class="mx-4 px-4 py-3 bg-accent text-gray-900 text-xs font-semibold rounded hover:bg-secondary hover:text-white" href="#">Learn More</a>
          </div>
        </div>
      </div>
      <div class="hidden lg:block lg:w-1/2" style="clip-path:polygon(10% 0, 100% 0%, 100% 100%, 0 100%)">
        <div class="h-full object-cover">
          <img src="~/assets/images/library.jpg">
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
</script>
