<template>
  <div class="details container">
    <h1 class="page-header">{{customer}}'s age {{age}}</h1>
    <form v-on:submit="getPlayerInfos">
    <button type="submit" class="btn btn-primary">Submit</button>
    </form>
  </div>
</template>
<script>

export default {
  name: 'Hello',
  data () {
    return {
      customer: '',
      age: 0
    }
  },

  methods: {
    fetchCustomer () {
      var api = 'http://localhost:8001'
      this.$axios.get(api).then((response) => {
        console.log(response.data)
        this.customer = response.data
      }).catch(function (error) {
        console.log(error)
      })
    },

    getPlayerInfos (e) {
      var reqUrl = 'http://localhost:8001/hello_1'
      const data = new FormData()
      data.append('name', 'GeekPanshi')
      data.append('age', this.age)
      this.$axios.post(reqUrl, data)
        .then((response) => {
          console.log(response.status)
          console.log(response.data)
          this.customer = response.data['name']
          this.age = response.data['age']
        }).catch(function (error) {
          console.log(reqUrl)
          console.log(error)
        })
    }
  },
  created: function () {
    this.fetchCustomer()
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
