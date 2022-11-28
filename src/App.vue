<template>
  <h1>{{title}}</h1> 
  <p>Welcome ... !</p>
  <div v-if="showModal">
    <div>
      <Modal theme="" @close="toggleModel">
        <template v-slot:links>
          <a href="#">Sign up</a>
          <a href="#">More</a>
        </template>
        <h1>Giveaway</h1>
        <p>Grab your token here !</p>
      </Modal>
    </div>
  </div> 
  <button @click.alt="toggleModel">Open Modal (Alt)</button>
</template>

<script>
import Modal from './components/Modal.vue';

  export default {
    name: 'App',
    components: { Modal },
    data(){
      return {
        title: 'My First Vue App',
        header: 'Sign up for the Giveaway',
        text:'First come first served !',
        showModal: false,
      }
    },
    methods: {
      toggleModel(){
        this.showModal = !this.showModal;
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
  h1{
    border-bottom: 1px solid #ddd;
    display: inline-block;
    padding-bottom: 10px;
  }
</style>
