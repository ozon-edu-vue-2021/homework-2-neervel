<template>
  <div >
    <div 
      @click="changeVisibility"
      class="directory-name"
      @mouseenter="togglePath"
      @mouseleave="togglePath"
    >
      {{ directoryIcon }} {{ name }}
      <span 
        v-if="visiblePath"
        class="file-path"  
      >{{ parentPath }}</span>
    </div> 
    <div v-if="isOpen">
        <node 
            v-for="(item, i) in content"
            :key="`${item.name}-${i}`"
            :item="item"
            style="margin-left: 20px;"
            :parentPath="parentPath"
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
    },
    parentPath: {
      type: String
    }
  },
  computed: {
    directoryIcon() {
      return this.isOpen ? '📂' : '📁'
    }
  },
  data() {
    return {
      isOpen: false,
      visiblePath: false
    }
  },
  methods: {
    changeVisibility() {
      this.isOpen = !this.isOpen
    },
    togglePath() {
      this.visiblePath = !this.visiblePath
    }
  }
}
</script>

<style scoped>
.directory-name {
  cursor: pointer;
  transition: .2s;
  height: 25px;
}
.directory-name:hover {
  background-color: rgba(91, 115, 252, 0.3)
}
.file-path {
  font-size: 14px;
  color: rgba(0, 0, 0, 0.3);
  margin-left: 30px;
}
</style>