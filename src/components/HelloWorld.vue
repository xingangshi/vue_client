<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <h2>This message is from nodejs</h2>
    <h3>The following message is from rust-server</h3>
    <router-link to="/hello">Hello, from server !</router-link>
  </div>
</template>

<script>
export default {
  name: 'Hello_World',
  data () {
    return {
      msg: 'This is demo of nodejs + rust'
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: normal;
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
