<script setup>
// Import
import upperCaseFirstChar from "@/helpers/js/upperCaseFirstChar";

// Props
const props = defineProps({
  subcategory: Object,
});

// Route parameters
const route = useRoute();

// Image placeholder
const imagePlaceholder = "./img/subcategories/placeholder.jpg";

// Function to replace broken image with a placeholder
function replaceImgByDefault(e) {
  e.target.src = imagePlaceholder;
}
</script>

<template>
  <NuxtLink class="subcategory-card" :to="route.path + '/' + subcategory.slug">
    <img
      :src="subcategory.image"
      @error="replaceImgByDefault"
      :alt="subcategory.title"
      class="subcategory-card__image"
    />
    <h2 class="subcategory-card__title">
      {{ upperCaseFirstChar(subcategory.title) }}
    </h2>
  </NuxtLink>
</template>

<style lang="scss" scoped>
.subcategory-card {
  display: flex;
  flex-direction: column;
  align-items: center;
  padding: 15px;
  margin-bottom: 15px;
  border-radius: 10px;
  background: $color-background;
  box-shadow: $shadow-card;
  flex-basis: 130px;
  flex-grow: 1;

  &__image {
    height: 150px;
    width: 150px;
    margin-bottom: 10px;
  }

  &__title {
    text-align: center;
    font-size: 20px;
    margin-bottom: 10px;
  }
}

.subcategory-card:nth-child(even) {
  margin-left: 15px;
}

@media (max-width: 375px) {
  .subcategory-card {
    flex-basis: 155px;
  }
  .subcategory-card:nth-child(even) {
    margin-left: 0;
  }
}
</style>
