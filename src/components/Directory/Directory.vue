<template>
  <div >
    <span 
      @click="changeVisibility"
      class="directory-name"
    >📁 {{name}}</span> 
    <div v-if="isOpen">
        <node 
            v-for="(item, i) in content"
            :key="`${item.name}-${i}`"
            :item="item"
            style="margin-left: 8px;"
          />
    </div>
     
  </div>
</template>

<script>

export default {
  name: 'Directory',
  components: {
    Node: () => import('../Node/Node.vue')
  },
  props: {
    name: {
      type: String,
      default: 'name'
    },
    content: {
      type: Array,
      default:() => ([])
    }
  },
  data() {
    return {
      isOpen: false
    }
  },
  methods: {
    changeVisibility() {
      this.isOpen = !this.isOpen
    }
  }
}
</script>

<style scoped>
.directory-name{
  cursor: pointer;
}
</style>