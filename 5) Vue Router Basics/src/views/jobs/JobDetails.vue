<template>
  <h1>Job Details Page</h1>
  <p>the job id (from the url) is {{ $route.params.id }}</p>
  <p>the job id (from props) is {{ id }}</p>

  <div v-if="job">
    <h2>{{ job.title }} </h2>
    <p>{{ job.details }}</p>
  </div>
  <div v-else>
    <p>Loading Job Details...</p>
  </div>
</template>

<script>
export default {
  props: ['id'], // comes from params from the Jobs.vue component
  data() {
    return {
      // id: this.$route.params.id
      job: null
    }
  },
  mounted() {
    fetch('http://localhost:3000/jobs/' + this.id) // returns a promise
      .then(res => res.json()) // this also returns a promise
      .then(data => this.job = data) // data is a job hashes, so we're setting this.job to be the job hash we get back
      .catch(err => console.log(err.message)) // in case something goes wrong
  }
}
</script>

<style>

</style>