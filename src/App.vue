<template>
  <div id="app">
    <p class="testData">
      {{ testData }}
    </p>
    <!--<router-view/>-->
  </div>
</template>

<script>
export default {
  name: 'App',
  data () {
    return {
      testData: '111'
    }
  },
  mounted () {
    let self = this
    axios.get('/api/test/getData')
      .then((response) => {
        self.testData = response.data.result.value
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
