<template>
  <div >
    <div v-if="item.type==='directory'">
      <directory
        :name="item.name"
        :content="item.contents"
      />
    </div>
    <div  v-else>
      <file
        :name="item.name"
        :type="item.type"
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
    }
  }
}
</script>

<style>

</style>