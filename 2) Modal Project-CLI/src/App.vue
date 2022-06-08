<template>
  <div>
    <img alt="Vue logo" src="./assets/logo.png" />
    <div v-if="showModal">
      <Modal :header="header" :text="text" theme="sale" />
    </div>
    <br>
    <button @click="toggleModal">open modal</button>
  </div>
</template>

<script>
import Modal from "./components/Modal.vue";

export default {
  name: "App",
  components: {
    Modal,
  },
  data() {
    return {
      header: "example of a prop being passed from App.vue to this Modal.vue component...",
      text: "modal content",
      showModal: false
    }
  },
  methods: {
    toggleModal() {
      this.showModal = !this.showModal
    }
  }
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
