<template>
  <h1>{{title}}</h1>
  <div v-if="showModal2">
    <!-- pass in props -->
    <!-- <Modal :header="header" :text="text" :sale="sale" @close="toggleModal"/> -->
    <Modal :sale="sale" @close="toggleModal2">
      <template v-slot:form>
        <form>
          <label for="fname">First name:</label><br>
          <input type="text" id="fname" name="fname"><br>
          <label for="lname">Last name:</label><br>
          <input type="text" id="lname" name="lname">
        </form>
      </template>
      <h1>Sale Giveaway!</h1>
      <p>grab your free copy now</p>
    </Modal>
  </div>
  <button @click="toggleModal">open modal</button>
  <button @click="toggleModal2">open modal 2</button>

</template>

<script>
import Modal from './components/Modal'

export default {
  name: "App",
  components: {
    Modal
  },
  data() {
    return {
      title: 'my Vue App',
      header: 'Sign up for the giveaway!',
      text: 'Grab your free copy now',
      sale: 'sale',
      showModal: false,
      showModal2: false
    }
  },
  methods: {
    toggleModal() {
      this.showModal = !this.showModal
    },
    toggleModal2() {
      this.showModal2 = !this.showModal2
    }
  }
};
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
  border-bottom: 1px solid #fff;
  display: inline-block;
}
</style>
