<template>
  <h1>{{title}}</h1>
  <p>Kia ora ...</p>
  <teleport to="#modals" v-if="showModal">
    <Modal theme="custom" @close="toggleModal">

      <template v-slot:test>
        <a href="#">Look</a>
        <a href="#">Hide</a>
      </template>

      <h1>Kei te pehea koe?</h1>
      <p>Kei te pai au. Kei te aha koe?</p>

    </Modal>
  </teleport>
  <teleport to="#modals" v-if="showElse">
    
    <Modal @close="toggleElse">

      <template v-slot:links>
        <a href="#">Enrol now</a>
        <a href="https://vuejs.org/guide/quick-start.html#creating-a-vue-application">More details</a>
      </template>
      
      <h1>No hea ia?</h1>

    </Modal>

  </teleport>
  <button @click="toggleModal">
    Open modal
  </button>
  <button @click="toggleElse">
    Open else
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
      // New property
      showModal: false,
      showElse: false
    }
  },
  methods:{
    toggleModal(){
      this.showModal = !this.showModal
    },
    toggleElse(){
      this.showElse = !this.showElse
    }
  }
}
</script>

<style>
#app, #modals {
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
button {
        color: #333;
        padding: 8px;
        border: 1px solid purple;
        border-radius: 4px;
        text-decoration: none;
        margin: 10px;
}
</style>
