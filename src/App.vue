<template>
<div>
 
<h1>{{title}}</h1>
 <p> welcome ..</p>
<div v-if="showModal">
  <Modal  header="sing up for give" text="Grab your loren" theme="sale" @close='toggel'>
    <template v-slot:link>
      <a href="#">sing up</a> 
      <a href="#">more</a>
    </template>
  <p>Giv your</p>
  <p>lorem ipsum dolor sit amet</p>
  </Modal>
</div>
<button @click.alt="toggel()">Open Modal</button>
</div>

 
</template>

<script>
import Modal from './components/Modal'
export default {
  name: 'App',
  components:{Modal},
  data() {
    return {
      title: 'Hi vue app',
      showModal: false,
      
    }
  },
  methods: {
    toggel() {
      this.showModal=!this.showModal

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
  padding-bottom:10px;
}
</style>
