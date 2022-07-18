<template>
   <h1>hi</h1>
   <div v-if="showModal">
     <Modal :header="header" :content="content" :theme="theme" @close="showModal=false" />
   </div>
   <button @click="showModal=true" style="margin-bottom:6px;">Open Modal</button> <br>
   <div v-if="deleteModal">
     <Modal :header="header" content="Are you sure you want to delete?" theme="delete" @close="deleteModal=false" />
   </div>
   <button @click="deleteModal=true">Delete Modal</button>
</template>

<script>
/* eslint-disable */
import Modal from "./components/Modal.vue";
export default {
    data(){
      return {
        header: "Login Success",
        content : "Welcome",
        theme: "success",
        showModal : false,
        deleteModal : true
      }
    },
    components: {
      Modal
    }

}
</script>

<style scoped>
  h1 {
    color: blue;;
  }
</style>