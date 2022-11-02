<template>
  <input type="number" min="0" max="2022" placeholder="search for a year" v-model="year"/>
  <button @click="getYearInfo">Wha' happen?</button>
</template>

<script>
const baseUrl = 'http://numbersapi.com/';

export default {
  name: 'HelloWorld',
  emits: ['addNewYearFact'],
  data() {
    return {
      year: ''
    }
  },
  methods: {
    getYearInfo() {
      let reqUrl = baseUrl + this.year.toString() + '/year';
      console.log(reqUrl);

      fetch(reqUrl)
        .then((response) => response.text())
        .then((text) => this.$emit('addNewYearFact', text));
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
$lime-green: #42b983;
$darker-green: darken($lime-green, 20%);
$darkest-green: darken($lime-green, 60%);

@mixin list-item-boilerplate($color) {
  border: 1px solid $color;
  background: rgba(100,100,100,0.3);
}

h3 {
  margin: 40px 0 0;
}
a {
  color: $lime-green;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;

  @include list-item-boilerplate($darker-green);

  a {
    color: darken(violet, 50%);
  }
}
</style>
