<template>
  <div class="backdrop">
    <div class="modal">
      <p>modal content</p>
    </div>
  </div>
</template>

<style>
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
</style>