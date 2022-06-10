<template>
<!-- the .self on @click.self means that you have to click on the backdrop to close the modal... -->
<!-- unlike before the .self, clicking on the modal will no longer close the modal, even though it's a part of the backdrop... -->
  <div class="backdrop" @click.self="closeModal">
    <div class="modal" :class="{ sale: theme === 'sale' }">
      <!-- the header value below is a prop passed down to this component from a parent component... -->
      <h3>{{ header }}</h3> 
      <p>{{ text }}</p>
    </div>
  </div>
</template>

<script>
export default {
  props: ["header", "text", "theme"],
  data() {},
  methods: {
    closeModal() {
      this.$emit('close')
    }
  }
};
</script>


<style scoped>
.modal {
  width: 400px;
  padding: 20px;
  margin: 96px auto;
  background: white;
  border-radius: 8px;
}

.backdrop {
  top: 0;
  position: fixed;
  background: rgba(0, 0, 0, 0.5);
  width: 100%;
  height: 100%;
}

.modal.sale {
  background: purple;
  color: white
}

.modal.sale h1 {
  color: white
}
</style>