<template>
  <div id="app">
    <Money v-model="price" clearable placeholder="请输入金额" />
  </div>
</template>

<script>
import Money from './components/Money.vue'
export default {
  name: 'App',
  components: {
    Money
  },
  data () {
    return {
      price: 0
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
  margin-top: 60px;
}
</style>
