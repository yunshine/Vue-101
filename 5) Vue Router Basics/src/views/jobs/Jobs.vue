<template>
  <h1>Jobs</h1>
  <div v-for="job in jobs" :key="job.id" class="job">
    <router-link :to="{ name: 'JobDetails', params: { id: job.id } }">
      <h2>{{ job.title }}</h2>
    </router-link>
  </div>
</template>

<script>
export default {
  data() {
    return {
      jobs: [
        // { title: 'UX Designer', id: 309, details: 'lorem' },
        // { title: 'Web Developer', id: 718, details: 'lorem' },
        // { title: 'Vue Developer', id: 122, details: 'lorem' }

      ]
    }
  },
  // a good place for fetching data is the mounted lifecycle hook:
  mounted() {
    fetch('http://localhost:3000/jobs') // returns a promise
      .then(res => res.json()) // this also returns a promise
      .then(data => this.jobs = data) // data is an array of job hashes, so we're setting this.jobs to be the array we get back
      .catch(err => console.log(err.message)) // in case something goes wrong
  }
}
</script>

<style>
.job h2 {
  background: #f4f4f4;
  padding: 20px;
  border-radius: 10px;
  margin: 10px auto;
  max-width: 600px;
  cursor: pointer;
  color: #444;
}
.job h2:hover {
  background: #ddd;
}
.job a {
  text-decoration: none;
}
</style>