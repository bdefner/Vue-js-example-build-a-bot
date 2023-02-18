<template>
  <header>
    <nav>
      <ul class="nav-item">
        <li><img class="logo" src="./assets/build-a-bot-logo.png" /> Build-a-Bot</li>
      </ul>
    </nav>
  </header>
  <main>
    <RobotBuilder />
  </main>
</template>

<script>
import RobotBuilder from './build/RobotBuilder.vue';

// import HomePage from './home/HomePage.vue';

export default {
  name: 'App',
  components: {
    RobotBuilder,
  },
};
</script>

<style>
body {
  margin: 0;
  padding: 100px;
  box-sizing: border-box;
  background-color: #333;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}

main {
  margin: 0 auto;
  display: flex;
  justify-content: center;
  max-width: 1024px;
  min-height: 300px;
  background: whitesmoke;
}

header {
  background-color: black;
  width: 1084px;
  margin: 0 auto;
  color: whitesmoke;
}
ul {
  padding: 3px;
  display: flex;
  list-style: none;
}

nav {
  display: flex;
  justify-content: space-between;
  align-items: center;
}
.nav-item {
  display: inline-block;
  padding: 5px 10px;
  font-size: 22px;
  border-right: 1px solid #bbb;
}
.logo {
  vertical-align: middle;
  height: 30px;
}
</style>
