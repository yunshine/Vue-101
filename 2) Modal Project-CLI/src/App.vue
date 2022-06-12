<template>
  <div>
    <img alt="Vue logo" src="./assets/logo.png" />
    <div v-if="showModal">
      <!-- <Modal :header="header" :text="text" theme="sale" @close="toggleModal" /> -->
      <Modal theme="sale" @close="toggleModal">

        <!-- the template below is for named slots named 'links' -->
        <template v-slot:links>
          <a href="#">sign up</a>
          <br>
          <a href="#">more info</a>
        </template>


        <h3>Some slot info...</h3>
        <h4>Some more slot info...</h4>
        <div class=actions>
          
        </div>
      </Modal>
    </div>
    <br>
    <button @click.shift="toggleModal">open modal (hold shift)</button>
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
