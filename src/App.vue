<template>
  <HelloWorld @add-new-year-fact="addNewYearFact"/>
  <DisplayList :yearfacts="yearfacts"/>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import DisplayList from './components/DisplayList.vue'

export default {
  name: 'App',
  components: {
    HelloWorld,
    DisplayList
  },
  data() {
    return {
      yearfacts: []
    }
  },
  methods: {
    addNewYearFact(text) {
      this.yearfacts.push(text);
    }
  }
}
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
