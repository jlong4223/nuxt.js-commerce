<template>
  <div>
    <h1>Products</h1>
    <product-list :products="products"></product-list>
  </div>
</template>

<script>
import commerce from "~/common/commerce";
import ProductList from "../../components/ProductList.vue";
export default {
  components: { ProductList },

  async asyncData() {
    const { data: products } = await commerce.products.list();
    return {
      products,
    };
  },
};

/* Here I'm making a request to Commerce.js for just our products, and rendering all components using the custom product-list component I made. */
</script>
