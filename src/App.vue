<template>
  <h1>{{title}}</h1>
  <p>Kia ora ...</p>
  <div v-if="showModal">
    <Modal :header="header" :text="text" theme="custom"/>
  </div>
  <button @click="toggleModal">
    Open modal
  </button>
</template>

<script>
import Modal from './components/Modal.vue'

export default {
  name: 'App',
  components: {Modal},
  data(){
    return{
      title: 'My First Vue App:)',
      header: 'Sign up for my newsletter',
      text: 'It is cool, it is awesome!',
      // New property
      showModal: false
    }
  },
  methods:{
    toggleModal(){
      this.showModal = !this.showModal
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
h1 {
  border-bottom: 1px solid #ddd;
  display: inline-block;
  padding-block: 10px;
}
</style>
