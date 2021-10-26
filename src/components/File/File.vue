<template>
  <div 
    class="file-item"
  >
     {{ itemIcon }} {{ name }}
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
    }
  },
  data() {
    return {
      selected: false
    }
  },
  computed: {
    itemIcon() {
      return this.type==="file" ? '📄' : '🔗'
    }
  }
}
</script>

<style>
.file-item {
  margin-left: 10px;
  cursor: pointer;
  transition: .2s;
}
.file-item:hover {
  background-color: rgba(91, 115, 252, 0.3)
}
</style>