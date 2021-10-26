<template>
  <div class="node">
    <div v-if="item.type==='directory'">
      <directory
        :name="item.name"
        :content="item.contents"
        :parentPath="path"
      />
    </div>
    <div  v-else>
      <file
        :name="item.name"
        :type="item.type"
        :parentPath="path"
      />
    </div>
  </div>
</template>

<script>
export default {
  name: 'Node',
  components: {
    Directory: () => import('../Directory/Directory.vue'),
    File: () => import('../File/File.vue')
  },
  props: {
    item: {
      type: Object
    },
    parentPath: {
      type: String,
      default: () => ('')
    }
  },
  computed: {
    path() {
      return this.parentPath + '/' + this.item.name
    }
  }
}
</script>

<style>

</style>