<template>
  <div id="app">
    <div>
      <NumPass userPassword="123456789" @password-match="passMatch" /> 
    </div>
  </div>
</template>

<script>


import NumPass from './components/NumericalPasswordInput.vue'

export default {
  name: 'App',
  components: {
    NumPass
  },
  methods: {
    passMatch(payload) {
      window.alert(payload);
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
  width: 100%;
  height: 100%;
  display: flex;
  flex-direction: row;
  justify-content: center;
  margin-top: 50px;
}
</style>

