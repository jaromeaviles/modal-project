<template>
  <h1>Welcome to Vue!</h1>
  <br />
  <button @click="toggleModal">Show Modal 1</button>
  <button @click="toggleModalTwo">Show Modal 2</button>

  <teleport to="#modals" v-if="isShowModal">
    <Modal @close="toggleModal">
      <h2>Modal 1</h2>
      <p>Welcome to Modal 1</p>

      <template v-slot:link>
        <a href="#">Signup</a>
      </template>
    </Modal>
  </teleport>

<teleport to="#modals" v-if="isShowModalTwo">
  <Modal @close="toggleModalTwo">
      <h2>Modal 2</h2>
      <p>Welcome to Modal 2</p>
  </Modal>
</teleport>

</template>

<script>
import Modal from "./components/Modal.vue";

export default {
  name: 'App',
  components: { Modal },
  data() {
    return {
      isShowModal: false,
      isShowModalTwo: false
    }
  },
  methods: {
    toggleModal() {
      this.isShowModal = !this.isShowModal;
    },
    toggleModalTwo() {
      this.isShowModalTwo = !this.isShowModalTwo;
    }
  }
}
</script>

<style lang="scss">
#app, #modals {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
