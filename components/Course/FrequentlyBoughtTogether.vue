<script setup>
// Define props for dynamic data
const props = defineProps({
  courseData: {
    type: Object,
    required: true,
  },
});
</script>

<template>
  <div class="flex items-start p-4 space-x-4 w-[80%]">
    <!-- Thumbnail Image -->
    <div class="w-48 h-32">
      <img
        :src="courseData.thumbnail"
        alt="Product Thumbnail"
        class="w-full h-full object-cover border border-gray-200"
      />
    </div>

    <!-- Product Details -->
    <div class="flex flex-col flex-1 space-y-1.5">
      <!-- Title -->
      <h3 class="text-lg font-semibold text-gray-900">
        {{ courseData.title }}
      </h3>

      <!-- Author Information -->
      <div class="flex items-center space-x-2 text-sm text-gray-600">
        <span class="font-semibold">{{ courseData.authors.join(", ") }}</span>
      </div>

      <!-- Rating and Reviews -->
      <div class="flex items-center space-x-2 text-sm text-gray-600">
        <SharedRatingStars :rating="courseData.rating" />
        <span>({{ courseData.reviews.toLocaleString() }})</span>
      </div>

      <div class="">
        <!-- Bestseller Badge -->
        <span
          v-if="courseData.isBestseller"
          class="bg-yellow-200 text-black font-semibold px-2 py-1 mt-2"
        >
          Bestseller
        </span>
      </div>
    </div>

    <!-- Pricing Information -->
    <div class="text-right">
      <p class="text-lg font-bold text-gray-900">
        {{ courseData.discountedPrice }}
      </p>
      <p class="text-sm line-through text-gray-500">
        {{ courseData.originalPrice }}
      </p>
    </div>
  </div>
</template>

<style scoped>
/* Additional styling, if necessary */
</style>
