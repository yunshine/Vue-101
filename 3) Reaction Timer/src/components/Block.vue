<template>
  <div class='block' v-if='showBlock'>click me</div>
</template>

<script>
export default {
  data() {
    return {
      showBlock: false
    }
  },
  props: ['delay'], 
  // life-cycle hooks...
  mounted() {
    console.log('component mounted...')
    console.log(`delay = ${this.delay}`)
    setTimeout(() => { this.showBlock = true }, this.delay)
  },
  updated() {
    console.log('component updated...')
  },
  unmounted() {
    console.log('unmounted...') // in this app, this component never actually unmounts; after all, there are no other pages to go to...
  }
}
</script>

<style>
  .block {
    width: 400px;
    border-radius: 20px;
    background: #0faf87;
    color: white;
    text-align: center;
    padding: 100px 0;
    margin: 40px auto;
  }
</style>