<template>
  <h1>{{title}}</h1>
  <p>Welcome</p>
  <div v-if="showModal">
  <Modal theme="sale" @close="toggleModal">
    <template v-slot:links>
      <a href="#">Sign up now</a>
      <a href="#">More info</a>
    </template>
    <h1>Ninja Giveaway</h1>
    <p>A great giveaway</p>
  </Modal>
  </div>
  <button @click.alt="toggleModal">open Modal(alt)</button>
</template>

<script>
import Modal from './components/Modal.vue'

export default {
  name: 'App',
  components: {Modal},
  data(){
    return{
      title: 'my first vue app',
      header: 'Sign up for the giveaway',
      text: "grab your ninja swag for half price",
      showModal: false
    }
  },
  methods: {
    toggleModal() {
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
</style>
