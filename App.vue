<template>
  <div id="app">
    <form action="" @submit="check">
      <label for="">User Name : </label><br>
      <input v-model="username" type="text" name="" id="" placeholder="Your name"><br>
      <label for="">Password : </label> <br>
      <input v-model="password" type="password" placeholder="Your password"> <br>
       <button >Submit</button>
    </form>
   
  </div>
</template>

<script>
export default {
  name: 'App',
  data(){return{  
    username: '',
    password: '',
    givename: 'aveen',
    givepassword: 1
  }},
  methods:{  
    check(e){  
      e.preventDefault();
      
      if(this.username !== this.givename && this.password !== this.givepassword){
       return
      }else { alert('okay')}
      
    }
  }

  
}
</script>

<style>

</style>
