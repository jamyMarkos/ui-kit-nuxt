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

// ReviewCard component:
const review = {
  reviewerName: "Md. Tanvir",
  rating: 5,
  datePosted: "2 months ago",
  reviewText:
    "This course is beneficial and informative. I have learned much about UI/UX design from scratch to final. Especially thanks to Daniel Schifano for his UI/UX design effort. I also thank Andrei Neagoie for the Web...",
  image: null,
};

const mostCourses = {
  image: "/images/course-thumbnail.png",
  logo: "/images/course-thumbnail.png",
  title: "Complete A.I. & Machine Learning, Data Science...",
  instructors: ["Andrei Neagoie", "Daniel Bourke"],
  rating: 4.6,
  reviews: 24457,
  totalHours: "44",
  lectures: "384",
  level: "All Levels",
  currentPrice: 11.99,
  originalPrice: 74.99,
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

      <div class="mt-4">
        <div>
          <h2 class="text-lg font-bold mb-4">Reviews</h2>
          <CourseReviewCard :reviewData="review" />
        </div>
      </div>

      <div class="mt-4">
        <div>
          <h2 class="text-lg font-bold mb-4">Most Courses</h2>
          <CourseMostCoursesCard :courseData="mostCourses" />
        </div>
      </div>
    </div>
  </main>
</template>

<style lang="scss" scoped></style>
