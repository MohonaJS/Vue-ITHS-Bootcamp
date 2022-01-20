<template>
  <div id="app">
  <!-- <button @click="shownum">Click me!!</button>
  <h1 v-if="show == 1">FrontEnd developer</h1>
  <h1 v-else-if="show == 2">Backend developer</h1> -->
  <button @click="showRan">Click to choose!!</button>
  <h1 v-if="show == 1">Frontend</h1>
  <h1 v-else-if=" show == 2">Backend</h1>


  </div>
</template>

<script>


export default {
  name: 'App',
  /* data(){return{  
    show: 0
  }},
  methods: {  
    shownum(){  
        this.show = Math.ceil(Math.random() * 2)
    }
  } */
  data(){return{  
    show : 0
  }},
  methods: {  
    showRan(){  
      this.show = Math.ceil(Math.random() * 2)
    }
  }
  




  
}
</script>

<style>

</style>
