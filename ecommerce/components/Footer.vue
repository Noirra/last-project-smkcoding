<template>
  <footer class="w-full border-t border-slate-200 py-6 bg-neutral">
    <div class="container flex justify-between space-x-8">
      <div class="w-1/4">
        <h1 class="text-lg font-bold text-primary mb-2 font-serif ">Astra Store</h1>
        <p class="text-sm text-slate-500">Astra Store adalah situs toko buku online yang menyediakan aneka buku
          berkualitas dan terlengkap, mulai dari buku-buku populer, e-book, pilihan, hingga buku-buku international
          lainya.</p>
      </div>
      <div class="w-1/4">
        <h2 class="text-lg font-bold text-primary mb-2">Quick Access</h2>
        <ul class="list-none">
          <li>
            <NuxtLink to="/" class="text-base text-slate-500 hover:text-secondary transition">Beranda</NuxtLink>
          </li>
          <li>
            <NuxtLink to="/product" class="text-base text-slate-500 hover:text-secondary transition">Buku</NuxtLink>
          </li>
          <li>
            <NuxtLink to="/cart" class="text-base text-slate-500 hover:text-secondary transition">Keranjang</NuxtLink>
          </li>
        </ul>
      </div>
      <div class="w-1/4">
        <h2 class="text-lg font-bold text-primary mb-2">Contact Me</h2>
        <p class="text-base text-slate-500 mb-2">Email: alky9684@gmail.com</p>

        <div class="flex justify">
          <a href="https://wa.me/082223062095" target="_blank" rel="noopener noreferrer">
            <img src="/images/wa.png" alt="WhatsApp" class="w-[35px] h-[35px] mx-2">
          </a>
          <a href="#" target="_blank" rel="noopener noreferrer">
            <img src="/images/fb.png" alt="Facebook" class="w-[35px] h-[35px] mx-2">
          </a>
          <a href="https://www.instagram.com/noirra_/" target="_blank" rel="noopener noreferrer">
            <img src="/images/ins.png" alt="Instagram" class="w-[35px] h-[35px] mx-2">
          </a>
          <a href="#" target="_blank" rel="noopener noreferrer">
            <img src="/images/tele.png" alt="Telegram" class="w-[35px] h-[35px] mx-2">
          </a>
        </div>

      </div>
    </div>
    <br>
    <div class="flex justify-center items-center">
    <p>&copy; 2023. Alif Ramadhan. All rights reserved</p>
  </div>
</footer></template>
