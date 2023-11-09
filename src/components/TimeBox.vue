<script setup lang="ts">
import { ref } from 'vue';

const days = ref(0);
const hours = ref(0);
const minutes = ref(0);
const seconds = ref(0);
const launchDate = new Date('22 November 2023');

setInterval(() => {
  const currDate = new Date();
  const launchTime = launchDate - currDate;

  seconds.value = parseInt(launchTime / 1000);
  minutes.value = parseInt(seconds.value / 60);
  hours.value = parseInt(minutes.value / 60);
  days.value = parseInt(hours.value / 24);
}, 1000);
</script>

<template>
  <div class="time__box">
    <p>
      {{ days }}d
    </p>
    <p>
      {{ hours % 24 }}h
    </p>
    <p>
      {{ minutes % 60 }}m
    </p>
    <p>
      {{ seconds % 60 }}s
    </p>
  </div>
</template>

<style scoped lang="scss">
.time__box {
  display: flex;
  justify-content: space-around;
  align-items: center;
  margin: 0 auto;
  width: 50%;
  gap: 20px;

  p {
    display: block;
    padding: 0 25px;
    line-height: 100px;
    border-radius: 10px;
    background-color: whitesmoke;
    box-shadow: 0 0 4px rgba(0, 0, 0, 0.2);
    font-weight: bold;
    font-size: 1.5em;
  }
}
</style>
