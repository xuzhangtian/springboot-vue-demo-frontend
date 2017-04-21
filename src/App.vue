<template>
  <div id="app">
    <img src="./assets/logo.png">
    <h2>{{msg}}</h2>
  </div>
</template>

<script>
  export default {
    data () {
      return {
        msg: ''
      }
    },
    created () {
      this.$http.get('/home')
        .then((response) => {
          this.msg = response.data
        })
        .catch((error) => {
          console.log(error)
        })
    }
  }
</script>

<style>
  #app {
    font-family: 'Avenir', Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    margin-top: 60px;
  }
</style>
