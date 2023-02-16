<template>
  <main>
    <HomePage />
  </main>
</template>

<script>
import HomePage from './components/HomePage.vue';

export default {
  name: 'App',
  components: {
    HomePage,
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
</style>
