<template>
  <div id="app">
    <el-form>
      <el-form-item label="金额">
        <Money v-model="price" clearable placeholder="请输入金额" />
      </el-form-item>
      <el-form-item label="实际值">
        {{price}}
      </el-form-item>
    
    </el-form>
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
  color: #2c3e50;
  margin: 60px auto;
  max-width: 750px;

}
</style>
