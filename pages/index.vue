<script setup lang="ts">
import Popap from "~/components/modals/Popap.vue";
import {ref} from 'vue'
let showModal = ref(false)

function openModal(isShow: boolean) {
  showModal.value = isShow
}
</script>
<template>
  <div class="home">
    <button class="home__button" @click="openModal(true)">Show popup</button>
    <Popap v-show="showModal" @close="openModal" />
  </div>
</template>
<style scoped>
.home {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: flex-end;
  height: 100vh;
}
.home__button {
  width: 200px;
  height: 40px;
  background-color: #000;
  border-radius: 12px;
  color: #fff;
  font-size: 16px;
  cursor: pointer;
  border-style: none;
  transition: .3s;
  margin-bottom: 100px;
}
.home__button:hover {
  background-color: #555;
  transition: .3s;
}
</style>