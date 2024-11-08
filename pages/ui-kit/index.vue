<script setup>
// CourseItem component:
const course = {
  title: "Complete Web design: from Figma to Webflow - 2024 UI",
  thumbnail: "/images/course-thumbnail.png",
  totalHours: "21.5",
  updatedDate: "11/2024",
  rating: 4.8,
  totalStudents: 86182,
  discountedPrice: "$11.99",
  originalPrice: "$74.99",
  isInWishlist: false,
};

// FrequentlyBoughtTogether component:
const courseData = {
  title: "Complete Web design: from Figma to Webflow - 2024 UI",
  thumbnail: "/images/course-thumbnail.png",
  discountedPrice: "$11.99",
  originalPrice: "$74.99",
  authors: ["Andrei Neagoic", "Daniel Schifano"],
  rating: 4.8,
  reviews: 33154,
  isBestseller: true,
};
</script>

<template>
  <main class="max-w-screen-lg mx-auto py-10">
    <div class="h-screen">
      <div>
        <h2>UI Kit</h2>
      </div>

      <div class="mt-4">
        <!-- Courses -->
        <CourseItem :course="course" />
      </div>

      <div class="mt-4">
        <div>
          <h2 class="text-lg font-bold mb-4">Frequently Bought Together</h2>
          <CourseFrequentlyBoughtTogether :courseData="courseData" />
        </div>
      </div>
    </div>
  </main>
</template>

<style lang="scss" scoped></style>
