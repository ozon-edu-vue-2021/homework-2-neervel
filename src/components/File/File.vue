<template>
  <div 
    class="file-name"
    @mouseenter="togglePath"
    @mouseleave="togglePath"
  >
     {{ itemIcon }} {{ name }}
     <span 
      v-if="visiblePath"
      class="file-path"  
    >{{ parentPath }}</span>
  </div>
</template>

<script>
export default {
  name: 'File',
  props: {
    name: {
      type: String
    },
    type: {
      type: String
    },
    parentPath: {
      type: String
    },
  },
  data() {
    return {
      selected: false,
      visiblePath: false
    }
  },
  computed: {
    itemIcon() {
      return this.type==="file" ? '📄' : '🔗'
    }
  },
  methods: {
    togglePath() {
      console.log(this.visiblePath)
      this.visiblePath = !this.visiblePath
    }
  }
}
</script>

<style>
.file-name {
  margin-left: 20px;
  cursor: pointer;
  transition: .2s;
  height: 20px;
  display: flex;
  align-items: center;
}
.file-name:hover {
  background-color: rgba(91, 115, 252, 0.3)
}
.file-path {
  font-size: 14px;
  color: rgba(0, 0, 0, 0.3);
  margin-left: 30px;
}
</style>