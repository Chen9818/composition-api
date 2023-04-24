<template>
  <HelloWorld :prop = mm @click='se'></HelloWorld>
  <h3>{{ num }}</h3>
  <!-- <h3>{{ ns }}</h3> -->
</template>

<script setup>
import HelloWorld from './components/HelloWorld.vue'
import { ref } from 'vue'

const mm = ref('from app page')
const num = ref(0)
// const ns = ref()

// eslint-disable-next-line no-return-assign
const se = () => (
  // eslint-disable-next-line no-sequences
  num.value++
)

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
</style>
