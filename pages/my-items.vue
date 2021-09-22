<template>
  <div class="container">
    <h1 class="my-5">My Rentals....</h1>
    <MyItem v-for="item in myRentals" :key="item.id" :item="item" />
  </div>
</template>

<script>
import { mapState } from 'vuex'

export default {
  // layout: 'no-nav',
  computed: {
    ...mapState(['myRentals']),
  },
}
</script>

<style scoped></style>
