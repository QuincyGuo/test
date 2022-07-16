<template>
  <div>
    <GrandFather :msg="title3" />
    <h1>{{title}}</h1>
    <button @click="settitle3">click</button>
  </div>
</template>

<script>
import GrandFather from './components/GrandFather.vue'

export default {
  name: 'App',
  components: {
    GrandFather,
  },
  data () {
    return {
      title: '12333',
    }
  },
  computed: {
    title3: {
      get () { return this.title; },
      set (newValue) {
        this.title = newValue;
      }
    }
  },
  methods: {
    settitle3 () {
      this.title3 = '888';
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
