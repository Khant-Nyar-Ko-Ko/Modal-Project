<template>
  <h1>{{ title }}</h1>
  <p>Welcome...</p>
  <Teleport to=".modals" v-if="showModal">
    <Modal theme="sale" @close="toggleModal">
      <template v-slot:links>
        <a href="#">Sign up</a>
        <a href="#">Login</a>
      </template>
      <h1>The Modal Test</h1>
      <p>Let's get started!</p>
    </Modal>
  </Teleport>
  <div v-if="showModal2">
    <Modal theme="sale" @close="toggleModal2">
      <template v-slot:links>
          <a href="#">Logout</a>
          <a href="#">More info</a>
      </template>
      <h1>This is the Challenge</h1>
      <p>I passed the challenge</p>
    </Modal>
  </div>
  <button @click="toggleModal">Open modal</button>
  <br>
  <button @click="toggleModal2">Open model 2</button>
</template>

<script>
import Modal from "./components/Modal.vue";

export default {
  name: "App",
  components: {
    Modal,
  },
  data() {
    return {
      title: "My First Vue App",
      showModal: false,
      showModal2: true
    };
  },
  methods: {
    toggleModal() {
      this.showModal = !this.showModal;
    },
    toggleModal2() {
      this.showModal2 = !this.showModal2
    }
  },
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
  border-bottom: 1px solid #ddd;
  display: inline-block;
  padding-bottom: 10px;
}
</style>
