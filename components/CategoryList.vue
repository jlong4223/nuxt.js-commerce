<template>
  <ul>
    <li v-for="category in categories" :key="category.slug">
      <n-link
        :to="{
          name: 'categories-slug',
          params: { slug: category.slug },
        }"
      >
        <category-view :category="category"></category-view>
      </n-link>
    </li>
  </ul>
</template>

<script>
import CategoryView from "./CategoryView.vue";
export default {
  components: { CategoryView },
  props: ["categories"],
};

/* Here I am mapping over the categories and creating a new link to show the category name - each category is passed as props to the category view component */
</script>
