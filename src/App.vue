<template>
  <div id="app">
    <div>
      <node
        :item="tree"
      />
    </div>
  </div>
</template>

<script>
import data from '../public/static/node_modules.js'
import Node from './components/Node/Node.vue'

export default {
  name: 'App',
  components: {
    Node
  },
  data(){
    return {
      tree: data
    }
  } 
}
</script>

<style>
#app {
  font-family: Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
