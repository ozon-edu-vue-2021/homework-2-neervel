<template>
  <div >
    <div 
      @click="changeVisibility"
      class="directory-name"
    >
      {{ directoryIcon }} {{ name }}
    </div> 
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
  computed: {
    directoryIcon() {
      return this.isOpen ? '📂' : '📁'
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
.directory-name {
  cursor: pointer;
  margin-left: 10px;
  transition: .2s;
}
.directory-name:hover {
  background-color: rgba(91, 115, 252, 0.3)
}
</style>