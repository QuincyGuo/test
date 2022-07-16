<template>
  <h1></h1>
</template>

<script>
// import AFather from './Father.vue'
export default {
  name: "GrandFather",
  props: ['msg'],
  watch: {
    msg: {
      immediate: true,
      handler (newVal, oldVal) {
        console.log(newVal + 'change to' + oldVal);
      }
    }
  }
}
</script>

<style>
</style>