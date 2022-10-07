<template>
  <h1>Job Details Page</h1>
  <p>the job id (from the url) is {{ $route.params.id }}</p>
  <p>the job id (from props) is {{ id }}</p>
</template>

<script>
export default {
  props: ['id'], // comes from params from the Jobs.vue component
  data() {
    return {
      // id: this.$route.params.id
  }
  }
}
</script>

<style>

</style>