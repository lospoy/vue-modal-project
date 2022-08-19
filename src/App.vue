<template>
  <h1>{{title}}</h1>
  <p>Welcome...</p>
  <div v-if='showModal'>
    <Modal theme='salse' @close='toggleModal'>
      <template v-slot:links>
        <a href="#">Sign up now</a>
        <a href="#">More info</a>
      </template>
      <h1>gtest</h1>
      <p>test</p>
    </Modal>
  </div>
  <button @click.alt="toggleModal">open modal (alt)</button>
</template>



<script>
import Modal from './components/Modal.vue'

export default {
  name: 'App',
  components: { Modal },
  data() {
    return {
      title: 'My First Vue App YAS',
      header: 'this is the header',
      text: 'Grab your ninja swag',
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
h1 {
  border-bottom: 2px solid #2c3e50;
  display: inline-block;
  padding-bottom: 10px;
}
</style>
