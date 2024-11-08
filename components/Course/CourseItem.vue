<script setup>
import { defineProps } from "vue";
/**
 * CourseItem component:
 * const course = {
 * title: 'Complete Web design: from Figma to Webflow - 2024 UI',
 * thumbnail: '/images/course-thumbnail.png',
 * totalHours: '21.5',
 * updatedDate: '11/2024',
 * rating: 4.8,
 * totalStudents: 86182,
 * discountedPrice: '$11.99',
 * originalPrice: '$74.99',
 * isInWishlist: false,
 * };
 */

// Define props for dynamic data
const props = defineProps({
  course: {
    type: Object,
    required: true,
  },
});

// Method to toggle wishlist status
const toggleWishlist = () => {
  props.course.isInWishlist = !props.course.isInWishlist;
};
</script>

<template>
  <div class="flex items-start w-[80%] space-x-4 p-4 border-b border-gray-200">
    <div class="flex space-x-4 w-2/3">
      <div class="w-20 h-20">
        <img
          :src="course.thumbnail"
          alt="Course Thumbnail"
          class="w-full h-full object-cover border border-gray-200"
        />
      </div>

      <div class="flex-1">
        <h3 class="text-lg font-semibold text-gray-900">
          {{ course.title }}
        </h3>

        <div class="flex items-center space-x-2 text-sm text-gray-600 mt-1">
          <span class="bg-yellow-200 text-black font-semibold px-3 py-1">
            Bestseller
          </span>
          <span class="text-green-950 font-semibold">
            {{ course.totalHours }} total hours
          </span>
          <span>•</span>
          <span>Updated {{ course.updatedDate }}</span>
        </div>
      </div>
    </div>

    <div class="flex justify-between items-start w-1/3">
      <div class="">
        <div class="flex items-center space-x-4">
          <div class="flex items-center">
            <span class="text-gray-800 font-semibold">{{ course.rating }}</span>
            <Icon name="tabler:star-filled" class="ml-1 text-yellow-600" />
          </div>
        </div>
      </div>

      <div class="">
        <div class="flex items-center">
          <Icon name="ic:round-people" class="text-xl text-gray-800" />
          <span class="ml-1">{{ course.totalStudents }}</span>
        </div>
      </div>

      <div class="flex items-center gap-x-3">
        <div>
          <div>
            <p class="text-lg font-bold text-gray-900">
              {{ course.discountedPrice }}
            </p>
            <p class="text-sm line-through text-gray-500">
              {{ course.originalPrice }}
            </p>
          </div>
        </div>

        <div>
          <button
            class="text-gray-500 border border-black/60 rounded-full w-10 h-10 hover:bg-gray-200 transition-colors duration-200 ease-linear"
          >
            <Icon
              :name="course.isInWishlist ? 'mdi:heart' : 'mdi:heart-outline'"
              class="text-lg text-black/60"
            />
          </button>
        </div>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped></style>
