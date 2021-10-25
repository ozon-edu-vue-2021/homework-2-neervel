<template>
  <div >
    <div v-if="item.type==='directory'" style="margin-left: 8px;">
      <directory
        :name="item.name"
        :content="item.contents"
      />
    </div>
    <div 
      v-else-if="item.type==='file'" 
      style="margin-left: 8px;"
    >
      <file
        :name="item.name"
      />
    </div>
    <div 
      v-else-if="item.type==='link'" 
      style="margin-left: 8px;"
    >
      <Link
        :name="item.name"
        style="margin-left: 8px;"
      />
    </div>
  </div>
</template>

<script>
export default {
  name: 'Node',
  components: {
    Directory: () => import('../Directory/Directory.vue'),
    File: () => import('../File/File.vue'),
    Link: () => import('../Link/Link.vue')
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