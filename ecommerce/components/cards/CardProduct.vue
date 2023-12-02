<script lang="ts" setup>
// import { Products } from '~/types/products';
const props = defineProps({
  product: {
    type: Object,
    default: {},
  }
});

import { productsStore } from "~/stores/buku";

const { baseStorageUrl } = useAppConfig();
const useProductsStore = productsStore();



const addCart = async () => {
  const payload = props.product;
  payload.isCart = !payload.isCart;
  await useProductsStore.updateProduct(payload, payload.id);
}
</script>



<template>
  <section class="bg-white shadow-card rounded-xl overflow-hidden w-[160px]">
    <div :class="`w-full h-[200px] p-3 bg-neutral-light`">
      <img :src="baseStorageUrl + props.product.image" class="w-full h-full object-contain"/>
    </div>
    <div class="px-3 pb-3 pt-5">
      <NuxtLink :to="`/product/${props.product.id}`"><h3 class="text-lg font-bold mb-2 text-limit limit-2 text-primary">{{ props.product.name }}</h3></NuxtLink>
      <div class="flex justify-between items-center">
        <span class="text-sm font-normal text-secondary">{{ props.product.category }}</span>
        <span class="text-sm font-normal text-secondary">Rp. {{ props.product.price }}</span>
      </div>
    </div>
  </section>
</template>




// const oneProduct = ref(props.product);

// watch(() => props.product, (currentValue, oldValue) => {
//   oneProduct.value = currentValue;
// })

// const addCart = () => {
//   oneProduct.value.isCart = !oneProduct.value.isCart
//   let localStorageData = localStorage.getItem("products");
//   let productOfCart: Products[] = [];

//   if (localStorageData) {
//     productOfCart = JSON.parse(localStorageData);
//   }

//   if (oneProduct.value.isCart) {
//     productOfCart.push(oneProduct.value);
//     localStorage.setItem("products", JSON.stringify(productOfCart));
//   } else {
//     productOfCart = productOfCart.filter((item) => item.id !== oneProduct.value.id);
//     localStorage.setItem("products", JSON.stringify(productOfCart));
//   }
// }