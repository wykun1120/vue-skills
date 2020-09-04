<template>
  <div id="app">
    <home-body></home-body>
    <home-header></home-header>
  </div>
</template>
<script>
// 引入多组件
const path = require('path')
const files = require.context('@/components/home', false, /\.vue$/)
const modules = {}

files.keys().forEach(key => {
  const name = path.basename(key, '.vue')
  modules[name] = files(key).default || files(key)
})

export default {
  components: modules,
  data () {
    return {

    }
  }
}
</script>
<style>
</style>
