<template>
  <div>
    <h2>Настроение котяка</h2>
    <input class="input" v-model="name" placeholder="Введите имя котика" />

    <p v-if="isHappy">{{ name }} сейчас {{ currentMood }} 😺</p>
    <p v-else>{{ name }} сейчас {{ currentMood }} 😿</p>

    <button @click="toggleMood">Поменять настроение</button>

    <h3>История настроений:</h3>
    <ul>
      <li v-for="(m, i) in moodHistory" :key="i">{{ m }}</li>
    </ul>
  </div>
</template>

<script setup>
import { ref } from 'vue'

const moods = ref(['Счастлив', 'Грусть', 'Злость', 'Удивление', 'Страх', 'Отвращение'])
const name = ref('Котяк')
const isHappy = ref(true)
const currentMood = ref(moods.value[0])
const moodHistory = ref([currentMood.value])

function toggleMood() {
  isHappy.value = !isHappy.value
  const randomIndex = Math.floor(Math.random() * moods.value.length)
  currentMood.value = moods.value[randomIndex]
  moodHistory.value.push(currentMood.value)
}
</script>

<style scoped>
.input {
  /* height: 6em;
  padding: 1.5em; */
  border-radius: 2px;
  will-change: filter;
  transition: filter 300ms;
}
.input:hover {
  filter: drop-shadow(0 0 2em #646cffaa);
}
.input.vue:hover {
  filter: drop-shadow(0 0 2em #42b883aa);
}
</style>