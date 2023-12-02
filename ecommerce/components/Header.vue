<script lang="ts" setup>
import { authStore } from '~/stores/auth';
import { storeToRefs } from 'pinia';
import useAuth from '~/composables/useAuth';
import { ref, onMounted, onUnmounted } from 'vue';

const { rmAuthorizationToken, rmRefreshToken, getAuthorizationToken } = useAuth();
const useAuthStore = authStore();

const isAuthenticated = ref();

onMounted(() => {
  isAuthenticated.value = getAuthorizationToken();
})

const logout = async () => {
  await rmAuthorizationToken();
  await rmRefreshToken();
  isAuthenticated.value = getAuthorizationToken();
  navigateTo("/");
}

const scrolled = ref(false);

const handleScroll = () => {
  scrolled.value = window.scrollY > 0;
};

onMounted(() => {
  window.addEventListener('scroll', handleScroll);
});

onUnmounted(() => {
  window.removeEventListener('scroll', handleScroll);
});
</script>

<template>
  <!-- Header -->
  <header class="w-full top-0 fixed z-50 border-slate-200 py-3 bg-accent transition-colors duration-300">
    <!-- Menu Mini -->
    <div class="container">
      <div class="flex justify-between items-center">
        <div class="flex items-center">
          <svg class="w-8 h-8 text-primary mr-2" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="3" d="M4 6h16M4 12h16m-7 6h7"></path>
          </svg>
          <NuxtLink to="/" class="text-xl font-bold font-serif text-primary">Astra Store</NuxtLink>
        </div>
        <nav class="flex items-center gap-8">
          <NuxtLink to="/" class="text-base text-primary rounded-lg px-1 py-0.4 hover:text-neutral transition hover:bg-primary">Beranda</NuxtLink>
          <NuxtLink to="/product" class="text-base text-primary rounded-lg px-1 py-0.4 hover:text-neutral transition hover:bg-primary">Buku</NuxtLink>
          <NuxtLink to="/cart" class="text-base text-primary rounded-lg px-1 py-0.4 hover:text-neutral transition hover:bg-primary">Keranjang</NuxtLink>
          <NuxtLink v-if="!isAuthenticated" to="/login" class="text-base bg-blue-600 px-4 py-1 text-white rounded-lg hover:bg-primary-dark transition">Login</NuxtLink>
          <div v-else class="text-base cursor-pointer bg-red-600 px-4 py-1 text-white rounded-lg hover:bg-primary-dark transition" @click="logout">Logout</div>
        </nav>
      </div>
    </div>
  </header>
</template>

<style scoped>
.bg-accent {
  background-color: rgb(0, 247, 219);
  color: #000000;
  transition: 0.4s;
}

header .flex.items-center {
  height: 100%;
}
header .flex.items-center svg {
  margin-top: -4px;
}
header .flex.items-center NuxtLink {
  margin-top: -2px;
}
</style>

