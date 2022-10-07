<template>
  <h1>Jobs</h1>
  <div v-for="job in jobs" :key="job.id">
    <router-link :to="{ name: 'JobDetails', params: { id: job.id } }">{{ job.title }}</router-link>
  </div>
</template>

<script>
export default {
  data() {
    return {
      jobs: [
        { title: 'UX Designer', id: 309, details: 'lorem' },
        { title: 'Web Developer', id: 718, details: 'lorem' },
        { title: 'Vue Developer', id: 122, details: 'lorem' }
      ]
    }
  }
}
</script>

<style>

</style>