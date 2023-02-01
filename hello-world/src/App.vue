<template>
  <div> {{ name }}</div>
  <!-- binding html -->
  <div v-html="greet"></div>
  <!-- example XSS attack -->
  <div v-html="hack"></div>
  <!-- binding to attributes -->
  <h2 v-bind:id="headingId">Hey</h2>
  <button v-bind:disabled="isDisabled">Bind</button>
  <!-- binding classes -->
  <h2 class="underline">Underlined text</h2>
  <h2 class="underline" v-bind:class="status">Status</h2>
  <h2 v-bind:class="isPromoted && 'promoted'">Promoted movie</h2>
  <!-- binding classes with ternary operator -->
  <h2 v-bind:class="isSoldOut ? 'sold-out' : 'new'">Soldout movie?</h2>
  <h2 v-bind:class="'new promoted'">Newly promoted movie</h2>
  <!-- binding classes : array -->
  <h2 v-bind:class="[isPromoted && 'promoted', isSoldOut ? 'sold-out' : 'new']">Array conditional rendering</h2>
  <!-- binding classes : object -->
  <h2 v-bind:class="{
    promoted: isPromoted,
    new: !isSoldOut,
    'sold-out': isSoldOut
  }">Array conditional rendering</h2>
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
      hack: `<a href="#" onClick="alert('hacked 3:)')">Click to win a prize!<a/>`,
      headingId: 'heading',
      isDisabled: false,
      status:'danger',
      isPromoted: true,
      isSoldOut: true
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

.underline{
  text-decoration: underline;
}

.danger{
  color: red;
}

.promoted{
  font-style: italic;
}

.new{
  color: green;
}
.sold-out{
  color: rgb(165, 22, 22);
}

</style>
