<template>
  <div id="app">
   <ol>
     <li v-for="fruit in fruits" v-bind:key="fruit">
       {{fruit}}
     </li>
   </ol>
  </div>
</template>

<script>

export default {
  name: 'App',
  data(){return{  
      fruits: [
        'apel','lisi','mango','komola'
      ]
  }}
  
}
</script>

<style>

</style>
