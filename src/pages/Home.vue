<template>
  <div class="home">
    <h1>{{ title }}</h1>
    <button v-on:click=getHomePage>Hello</button>
  </div>
</template>

<script>
export default {
  name: 'Home',
  props: {
    msg: String
  },
  data: function () {
      return {
          title: 'HOME'
      }
  },
  methods: {
      getHomePage: function() {
          this.title = "clicked"
          this.axios.get('http://localhost:8081')
          .then(response => this.title = response)
      }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
