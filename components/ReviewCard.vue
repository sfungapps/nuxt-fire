<template>
  <div class="review-card m-4 d-flex align-items-center">
    <!-- {{ review }} -->
    <div class="image-container mr-3">
      <img :src="review.picture.thumbnail" :alt="review.picture.thumbnail" />
    </div>
    <div class="text-container">
      <h5>{{ review.login.username }}</h5>
      <span>
        Lorem ipsum dolor sit amet consectetur, adipisicing elit. Sapiente,
        maiores!
      </span>
    </div>
  </div>
</template>

<script>
export default {
  props: ['review'],
}
</script>

<style scoped>
img {
  border-radius: 50%;
}
.review-card {
  display: inline-flex;
}
</style>
