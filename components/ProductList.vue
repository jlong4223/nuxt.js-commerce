<template>
  <ul>
    <li v-for="product in products" :key="product.permalink">
      <n-link
        :to="{
          name: 'products-permalink',
          params: { permalink: product.permalink },
        }"
      >
        <product-view :product="product"></product-view>
      </n-link>
    </li>
  </ul>
</template>

<script>
import ProductView from "./ProductView.vue";
export default {
  components: { ProductView },
  props: ["products"],
};
</script>
