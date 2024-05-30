<script setup lang="ts">
const emit = defineEmits(['close'])
import {ref} from 'vue'
let startAnimation = ref(false)


function closeModal() {
  startAnimation.value = true
  setTimeout(() => {
    emit('close', false)
    startAnimation.value = false
  }, 450)

}
</script>
<template>
  <div class="popup" :class="startAnimation ? 'hide' : false">
    <div class="popup__content">
      <span class="close" @click="closeModal">&#x2715;</span>
      <h1>Hello! I'am popup</h1>
    </div>
  </div>
</template>
<style scoped>
.popup {
  position: fixed;
  width: 100%;
  height: 100%;
  display: flex;
  align-items: center;
  justify-content: center;
  animation: showPopap 500ms linear;
}
.popup__content {
  width: 500px;
  height: 150px;
  border-radius: 10px;
  background-color: #5480c7;
  display: flex;
  align-items: center;
  justify-content: center;
  position: relative;
}
.close {
  position: absolute;
  right: -20px;
  top: -10px;
  cursor: pointer;
}
.hide {
  animation: hidePopup 500ms linear;
}

@keyframes showPopap {
  0% {
    opacity: 0;
    transform: translateY(26px);
  }
  100% {
    opacity: 1;
    transform: translateY(0);
  }
}

@keyframes hidePopup {
  0% {
    opacity: 1;
    transform: translateY(0);
  }
  100% {
    opacity: 0;
    transform: translateY(26px);
  }
}
</style>