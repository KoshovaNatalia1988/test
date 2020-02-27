<template>
  <div>
    <button @click='showModal' :visible="isModalVisible" >Oткрыть модальное окно</button>
    <Modal v-show="isModalVisible"  @close="closeModal">
      <template v-slot:header>
          <h1>Header</h1>
      </template>
      <template v-slot:main>
          <h1>Main</h1>
      </template>
      <template v-slot:footer>
          <h1>Footer</h1>
      </template> 
    </Modal>
    
  </div>
</template>

<script>
import Modal from './Modal'
export default {
  name: 'HelloWorld',
  data () {
    return {
      isModalVisible: false,
    }
  },
  components: {
    Modal: Modal
  },
  methods: {
    closeModal(noVisible) {
      this.isModalVisible = noVisible;
    },
   showModal() {
     this.isModalVisible = true;
   }
  }
}
</script>

<style  lang="scss">
</style>
