<template>
  <nav>
    <router-link to="/">Home</router-link> |
    <!-- <router-link to="/about">About</router-link> -->
    <router-link :to="{ name: 'about' }">About</router-link> |
    <router-link :to="{ name: 'jobs' }">Jobs</router-link>
  </nav>

  <button @click="redirect">Redirect</button>
  <button @click="back">Go Back</button>
  <button @click="forward">Go Forward</button>

  <router-view/>
</template>

<script>
export default {
  methods: {
    redirect() {
      this.$router.push('/') // $router.push is used to redirect the user to a route of our choosing
      // this.$router.push({ name: 'home' }) // alternate syntax
    },
    back() {
      this.$router.go(-1) // $router.go is used to move the user to routes in the browswer history
    },
    forward() {
      this.$router.go(1) // $router.go is used to move the user to routes in the browswer history
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

nav {
  padding: 30px;
}

nav a {
  font-weight: bold;
  color: #2c3e50;
}

nav a.router-link-exact-active {
  color: #42b983;
}

button {
  margin: 0 10px;
  padding: 10px;
  border: none;
  border-radius: 4px;
}
</style>
