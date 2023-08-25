<template>
  <h1>{{title}}</h1>
  <p>Kia ora ...</p>
  <div v-if="showModal">
    <Modal theme="custom" @close="toggleModal">
      <template v-slot:links>
        <a href="#">Enrol now</a>
        <a href="#">More details</a>
      </template>
      <h1>Kei te pehea koe?</h1>
      <p>Kei te pai au. Kei te aha koe?</p>

    </Modal>
    <Modal theme="project" @close="toggleModalTwo">
      <template v-slot:newlinks>
        <a href="#">New</a>
        <a href="#">Edit</a>
        <h1>Are you applying for work?</h1>
        <p>Check your status</p>
      </template>
    </Modal>
  </div>
  <button @click.alt="toggleModal">
    Open modal (Alt)
  </button>
  <button @click.alt="toggleModalTwo">
    Open new modal
  </button>
</template>

<script>
// Challenge
//  - create an extra button to open a different modal
//  - use the same modal component but pass in a different template (slot)
//  - use a different method (e.g. toggleModalTwo) and data (e.g. showModalTwo)

import Modal from './components/Modal.vue'

export default {
  name: 'App',
  components: {Modal},
  data(){
    return{
      title: 'Tena koutou katoa',
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
