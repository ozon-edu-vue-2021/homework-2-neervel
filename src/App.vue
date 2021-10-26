<template>
  <div id="app">
    <div class="file-tree">
      <div class="file-tree-header">
        <span class="file-tree__title">Route 256 • Explorer</span>
      </div>
      <div class="file-tree-body">
        <node
          :item="tree"
        />
      </div>
    </div>
  </div>
</template>

<script>
    import data from '../public/static/node_modules.js'
    export default {
        name: 'App',
        components: {
            Node: () =>
                import ('./components/Node/Node.vue')
        },
        data() {
            return {
                tree: data
            }
        }
    }
</script>

<style>
    body {
        margin: 0;
        background-color: #F2F4FF;
    }
    
    #app {
        font-family: Helvetica, Arial, sans-serif;
        -webkit-font-smoothing: antialiased;
        -moz-osx-font-smoothing: grayscale;
        color: #2c3e50;
        display: flex;
        align-items: center;
        justify-content: center;
        height: 100vh;
    }
    
    .file-tree {
        width: 90%;
        background-color: #fff;
        border-radius: 10px;
        filter: drop-shadow(5px 5px 20px rgba(0, 0, 0, 0.3));
    }
    
    .file-tree-header {
        background-color: #005bff;
        color: #fff;
        border-radius: 10px 10px 0 0;
        padding: 5px 15px;
    }
    
    .file-tree-body {
        padding: 10px 15px;
        height: 500px;
        max-height: 500px;
        overflow-y: scroll;
    }
</style>