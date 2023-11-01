<script setup>
import { ref } from 'vue'

let notification = ref(0)

function addValue() {
  notification.value++
  console.log(notification)
}

function decreaseValue() {
  if (notification.value >= 1) {
    notification.value--
  }
}

addValue()
</script>

<template>
  <div class="wrapper">
    <div class="profile">
      <div class="notification" v-if="notification >= 1">{{ notification }}</div>
    </div>
    <div class="button-wrapper">
      <div class="button" @click="decreaseValue">-</div>
      <div class="button" @click="addValue">+</div>
      <div v-if="notification == 0">Buuu! nadie te escribe 🤣</div>
      <div v-else>Revisa tu inbox 😊</div>
    </div>
  </div>
</template>

<style scoped>
.wrapper {
  background-color: rgb(168, 229, 248);
  width: 40%;
  border-radius: 8px;
  margin: 0 auto;
  padding-top: 32px;
}

.profile {
  background-color: orange;
  width: 200px;
  height: 200px;
  border-radius: 100%;
  margin: 0 auto;
  position: relative;
  background-image: url(https://sonicfangameshq.com/forums/showcase/kirby-gamble-galaxy-stories-v0-5-kirby-maker-update.1341/cover-image);
  background-size: cover;
}

.notification {
  position: absolute;
  background-color: red;
  width: 30px;
  height: 30px;
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  color: aliceblue;
  top: 0;
  right: 0;
  overflow: hidden;
}

.button-wrapper {
  text-align: center;
  margin-top: 12px;
  padding: 15px 0;
}

.button {
  background-color: rgb(1, 219, 128);
  border-radius: 4px;
  padding: 6px 0;
  font-weight: bold;
  color: aliceblue;
  width: 60px;
  display: inline-block;
  cursor: pointer;
}

.button:first-child {
  margin-right: 8px;
}

.button:last-child {
  margin-left: 8px;
}
</style>
