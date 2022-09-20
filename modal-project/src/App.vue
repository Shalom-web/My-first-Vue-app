<template>
  <h1>{{title}}</h1>
  <p>Welcome...</p>

<teleport to=".modals" v-if="showModal">
  <Modal theme="sale" @close="toggleModal">
    <template v-slot:links>
      <a href="#">Sign up now</a>
      <a href="#">More info</a>
    </template>
    <h1>Giveaway</h1>
    <p>Grab your free copy now!</p>
  </Modal>
</teleport>

<teleport to=".modals" v-if="showModalTwo">
  <Modal  @close="toggleModal">
    <h1>Sign up to the newsletter</h1>
    <p>For updates and promo codes</p>
  </Modal>
</teleport>

<button @click.alt="toggleModal">Open Modal (alt)</button>
<button @click="toggleModalTwo">Open Modal</button>

</template>

<script>

import Modal from './components/Modal.vue'
  export default{
    name: 'App',
    components: { Modal },
    data() {
      return {
        title: 'Welcome to Vue App',
        showModal: false,
        showModalTwo: false

      }
    },
    methods: {
      toggleModal(){
        this.showModal=!this.showModal
      },
      toggleModalTwo(){
        this.showModalTwo = !this.showModalTwo
      }
    }
  }
</script>


<style>
header {
  line-height: 1.5;
}
h1{
  border-bottom: 1px solid #ddd;
  display: inline-block;
  padding-bottom: 10px;
  color: rgb(0, 0, 0);
}
.logo {
  display: block;
  margin: 0 auto 2rem;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }
}
</style>
