<template>
  <h1>{{title}}</h1>
  <p>Kia ora ...</p>
  <div v-if="showModal">
    <Modal :header="header" :text="text" theme="custom" @close="toggleModal"/>
  </div>
  <button @click.alt="toggleModal">
    Open modal (Alt)
  </button>
</template>

<script>
import Modal from './components/Modal.vue'

export default {
  name: 'App',
  components: {Modal},
  data(){
    return{
      title: 'Welcome to Test',
      header: 'Sign up for Te Reo Maori',
      text: 'Ka pai!',
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
