<template>
  <div> {{ name }}</div>
  <!-- binding html -->
  <div v-html="greet"></div>
  <!-- example XSS attack -->
  <div v-html="hack"></div>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'App',
  // components: {
  //   HelloWorld
  // }
  data(){
    return{
      greet:'<b>Hello</b> ',
      name:"Imen",
      hack: `<a href="#" onClick="alert('hacked 3:)')">Click to win a prize!<a/>`
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
