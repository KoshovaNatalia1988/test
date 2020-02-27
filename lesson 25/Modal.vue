<template>
  <div class="modal-backdrop">
    <div class="modal">
      <button class="btn-close" @click="close">
        x
      </button>
      <header class="modal-wrapper">
        <slot name="header"></slot>
      </header>
      <main class="modal-wrapper">
        <slot name="main"></slot>
      </main>
      <footer class="modal-wrapper">
        <slot name="footer"></slot>
      </footer>
    </div>
  </div>
</template>

<script>
   export default {
     name:"Modal",
     props:{
         visible: Boolean,
     },
     data () {
         return {
         }
     },
     methods: {
      close() {
         this.$emit('close',this.visible);
      }
     }
   }
</script>

<style lang='scss'>
  .modal {
    width: 400px;
    height: 500px;
    background: #FFFFFF;
    position: relative;
    left: 50%;
    transform: translate(-50%);
  }
  .btn-close {
    font-size: 20px;
    padding: 10px;
    cursor: pointer;
    background: red;
    position: fixed;
    right: 0;
    }
  .modal-wrapper {
      padding: 30px;
  }
</style>