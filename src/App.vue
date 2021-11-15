<template>
  <div id="nav">
    <router-link to="/">Home</router-link> |
    <router-link to="/dcHeros">DC Heros</router-link> |
    <router-link to="/Calendar">Calendar</router-link> |
    <router-link to="/Markdown">Markdown</router-link> |
    <router-link to="/about">About</router-link> |
    <!-- same as below, use 2nd preferably -->
    <!-- <router-link to="{name: 'About'}">About</router-link> -->
    <!-- <router-link to="/jobs">Jobs</router-link> -->
    <router-link to="/jobs">Jobs</router-link>
  </div>

  <!-- <button @click="redirect">Redirect</button>
  <button @click="back">Go back</button>
  <button @click="forward">Go forward</button> -->
  <router-view/>

  <div id="footer">Made with ❤️ by PaulKing</div>
</template>

<script>
export default {
  methods: {
    redirect() {
      this.$router.push({ name: 'Home' })
    },
    back() {
      this.$router.go(-1)
    },
    forward() {
      this.$router.go(1)
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  /* text-align: center; */
  color: #2c3e50;
  /* box-sizing: border-box; */
}

#nav{
  padding: 30px;
  background: turquoise;
  margin: 0;
  text-align: center;
  /* align-items: center; */

}

#nav a {
  font-weight: bold;
  color: #2c3e50;
  text-decoration: none;
  padding: 10px;
  border-radius: 60px;
}

#nav a.router-link-exact-active {
  color: white;
  background-color: crimson;
}

#footer {
  position: bottom;
  bottom: 100;
  width: 100%;
  height: 30px;
  padding: 10px 10px 0 10px;
  text-align: center;
  font-weight: 700;
  /* margin-top: 500px; */
  font-size: 1.4rem;

}

button {
  margin: 0 10px;
  padding: 10px;
  border: none;
  border-radius: 4px;
  font-weight: bold;
  color: white;
  background-image: linear-gradient(0deg, aqua, red 70% 30%);
  border-bottom: 2px black solid;
}
</style>
