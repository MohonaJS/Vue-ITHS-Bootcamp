<template>
  <div id="app">
    

     <!--  <h1>Write ur random number {{num}}</h1>
      <input type="text" v-model="num" placeholder="write a number" > -->

     <!--  <form action="" @submit="prevent">
        <div>
          <label for="">Write ur text : </label> <br>
        <input type="text" @keydown.ctrl="prevent"> <br>
        </div>
        <button type="submit" >"Submit"</button>
      </form> -->
      


  </div>
</template>

<script>
export default {
  name: 'App',
  data(){  
    return{  
      text: ""
    }
  },
  methods: {  
    prevent(e){  
     e.preventDefault();
     alert("ok")
     
    }
  }
  
  
  /* data(){  return {  
    num:4
  }
  },
  methods: {  
    randomnum(){
    this.num = this.num = Math.random() + 1 
     
    }
  } */


}
</script>

<style>
form{
  background: rgb(185, 126, 126);
}
</style>
