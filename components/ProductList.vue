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

/* In the template above, i'm mapping over each of our products passed down through props, and returning a new link. The contents of the link is the Product component I made previously. */
</script>
