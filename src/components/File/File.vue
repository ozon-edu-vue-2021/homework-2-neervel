<template>
  <div>
    📄 {{ name }}
  </div>
</template>

<script>
export default {
  name: 'File',
  props: {
    name: {
      type: String
    }
  }
}
</script>

<style>

</style>