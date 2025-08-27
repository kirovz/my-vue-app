<script setup>
import HelloWorld from './components/HelloWorld.vue'
import Counter from './components/Counter.vue'
import MoodList from './components/MoodList.vue'
</script>

<template>
  <div>
      <HelloWorld msg="Страничка котька" />

    <a href="https://vite.dev" target="_blank">
      <img src="/vite.svg" class="logo" alt="Vite logo" />
    </a>
    <a href="https://vuejs.org/" target="_blank">
      <img src="./assets/vue.svg" class="logo vue" alt="Vue logo" />
    </a>
    <a href="https://1inch.io/" target="_blank">
      <img src="./assets/cripto-icons/1inch.svg" class="logo 1inch" alt="1inch logo" />
    </a>
  </div>
    <MoodList />
    <Counter />
</template>

<style scoped>
.logo {
  height: 6em;
  padding: 1.5em;
  will-change: filter;
  transition: filter 300ms;
}
.logo:hover {
  filter: drop-shadow(0 0 2em #646cffaa);
}
.logo.vue:hover {
  filter: drop-shadow(0 0 2em #42b883aa);
}
</style>
