<template>
  <h1>{{title}}</h1>
  <p>Welcome...</p>

  
  <teleport to='.modals' v-if='showModal'>
    <Modal theme='sale' @close='toggleModal'>
      <template v-slot:links>
        <a href="#">Sign up now</a>
        <a href="#">More info</a>
      </template>
      <h1>gtest</h1>
      <p>test</p>
    </Modal>
  </teleport>
  <button @click.alt="toggleModal">open modal (alt)</button>
<br />
<br />


  <div v-if='showModalTwo'>
    <Modal @close='toggleModalTwo'>
      <template v-slot:img>
        <img src="./assets/logo.png">
      </template>
    </Modal>
  </div>
  <button @click="toggleModalTwo">open modal two</button>

</template>



<script>
import Modal from './components/Modal.vue'

export default {
  name: 'App',
  components: { Modal },
  data() {
    return {
      title: 'My First Vue App YAS',
      showModal: false,
      showModalTwo: false,
    }
  },
  methods: {
    toggleModal() {
      this.showModal = !this.showModal
    },
    toggleModalTwo() {
      this.showModalTwo = !this.showModalTwo
    }
  }
}
</script>

<style>
#app, .modals {
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
