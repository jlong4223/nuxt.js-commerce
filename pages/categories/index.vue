<template>
  <div>
    <h1>Categories</h1>
    <category-list :categories="categories"></category-list>
  </div>
</template>

<script>
import commerce from "~/common/commerce";
import CategoryList from "../../components/CategoryList.vue";
export default {
  components: { CategoryList },
  async asyncData() {
    const { data: categories } = await commerce.categories.list();
    return {
      categories,
    };
  },
};

/* rendering the custom category-list component, and passing down categories from the asyncData request */
</script>
