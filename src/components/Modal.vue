<template>
  <div class="backdrop" @click.self="closeModal">
     <div class="modal" :class="{success:theme==='success', danger:theme==='delete'}">
        <h1>{{ header }}</h1>
        <p>{{ content }}</p>
        {{theme}}
     </div>
  </div>
</template>

<script>
export default {
   // accept the prop from App.vue
   props:['header', 'content', 'theme'],
    methods : {
      closeModal(){
        this.$emit("close")
      }
}
}
</script>

<style scoped>
  .backdrop {
    position: fixed;
    top: 0;
    background: rgba(0, 0, 0, 0.5);
    width: 100%;
    height: 100%;
  }
  .modal {
    width: 400px;
    padding: 20px;
    margin: 100px auto;
    background-color: white;
    border-radius: 10px;
  }
  p {
    font-style: normal;
  }
  .success {
    background-color: green;
    color: white;
  }
  .danger {
    background-color: crimson;
    color: white;
  }
</style>