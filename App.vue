<template>
  <div id="app">
    <button @click="showModal = true" class="button"> Show Modal  !! </button>
    <transition name="fade" appear>
      <div class="modal-overlay" @click="showModal = false" v-if="showModal"></div>
    </transition>

    <transition name="slide" appear>
        <div class="modal" v-if="showModal">
            <h1>Hello vue</h1>
            <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Quasi, ad?</p>
            <button class="button" @click="showModal = false">close</button>
        </div>
    </transition>
  </div>
</template>

<script>
export default {
  name: 'App',
  data(){return{  
      showModal: true
  }}
}
</script>

<style>
  *  {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
  }
  body{
    font-family: sans-serif;
  }
  #app {
    position: relative;

    display: flex;
    justify-content: center;
    align-items: center;

    width: 100vw;
    min-height: 100vh;
    overflow: hidden;
  }
  .button {
    appearance: none;
    outline: none;
    border: none;
    background: none;
    cursor: pointer;
    display: inline-block;
    padding: 15px 25px;
    background-image: linear-gradient(to right, blue, green);
    border-radius: 9px;

    color: white;
    font-size: 18px;
    font-weight: 700;
    box-shadow: 4px 4px rgb(13, 58, 58);
    transition: 0.4s ease-out;
  }
  .button:hover {
    box-shadow: 6px 6px rgba(83, 58, 58, 0.5);
  }
  .modal-overlay {
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    z-index: 98;
    background-color: rgba(104, 94, 94, 0.56);
    
  }
  .modal{
    position: fixed;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    z-index: 99;
    width: 100%;
    max-width: 400px;
    background-color: white;
    border-radius: 16px;
    padding: 30px;
  }
 .modal h1{
    color: white;
    font-size: 32px;
    font-weight: bold;
    margin-bottom: 15px;
  }

  .modal p{
    color: blue;
    font-size: 20px;
    margin-bottom: 15px;
  }
  .fade-enter-active, 
  .fade-leave-active {
    transition: opacity 0.5s;
  }
  .fade-enter,
  .fade-leave-to {
    opacity: 0;
  }
</style>
