<template>
  <div>
    <b-button v-b-modal.modal-1>Rent</b-button>
    <b-modal
      id="modal-1"
      ref="my-modal"
      centered
      no-close-on-backdrop
      hide-footer
      :title="product.title"
    >
      <p class="my-4">{{ product.snippet }}</p>
      <div class="calendar-container">
        <div class="text-container">
          <p>
            Lorem ipsum dolor sit, amet consectetur adipisicing elit. Beatae
            delectus fuga earum possimus quia voluptate. Consequatur accusamus
            dolore soluta totam!
          </p>
        </div>
        <!-- <vc-calendar :value="null" color="red" v-model="dateRange" /> -->
        <vc-date-picker
          :value="null"
          color="indigo"
          v-model="dateRange"
          is-range
        />
      </div>
      <hr />
      <!-- <p>{{ dateRange }}</p> -->
      <b-button
        id="show-btn"
        variant="outline-danger"
        @click="addOne(product.id)"
        >Order</b-button
      >
    </b-modal>
  </div>
</template>

<script>
import { mapActions } from 'vuex'

export default {
  props: ['product'],
  data() {
    return {
      dateRange: {
        start: '',
        end: '',
      },
    }
  },
  methods: {
    ...mapActions(['addItem']),
    hideModal() {
      this.$refs['my-modal'].hide()
    },
    addOne(id) {
      this.addItem(id)
      this.hideModal()
      this.$router.push('/my-items')
    },
  },
}
</script>

<style scoped>
button {
  width: 100%;
  border: none;
  padding: 0.5rem;
  color: white;
  font-weight: 700;
  padding: 1rem 4rem;
  border-radius: 100rem;
  background-color: rgb(231, 81, 43);
  color: white;
  font-weight: 700;
  transition: 0.5s;
}
.calendar-container {
  margin: 0 auto;
  display: flex;
  justify-content: space-between;
}
p {
  color: grey;
}
.text-container {
  padding: 0.5rem;
}
</style>
