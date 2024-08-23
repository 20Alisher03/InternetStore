<template>
  <div>
    <!-- Ваш контент здесь -->
    <button @click="showModal">Открыть модальное окно</button>
    <teleport to="body">
      <div v-if="isModalVisible" class="modal">
        <!-- Содержимое модального окна -->
        <button @click="closeModal">Закрыть</button>
      </div>
    </teleport>
  </div>
</template>

<script>
export default {
  data() {
    return {
      isModalVisible: false
    }
  },
  methods: {
    showModal() {
      this.isModalVisible = true
    },
    closeModal() {
      this.isModalVisible = false
    }
  }
}
</script>

<style scoped>
/* Стили для модального окна */
.modal {
  position: fixed;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  background-color: white;
  padding: 20px;
  box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
}
</style>
