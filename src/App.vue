<script setup>
import AppHeader from './components/Header.vue';
import QuizQuestion from './components/Question.vue';
import './assets/question.css';
</script>

<template>
  <AppHeader />

  <div class="progress-bar" />

  <main class="main">
    <QuizQuestion />
  </main>
</template>

<style scoped>
  .progress-bar {
    height: 4px;

    background-image: linear-gradient(to right, #0000FF 50%, #D8D7E1 50%);
  }

  .main {
    padding: 38px 16px 16px;
    background-color: #F8F7FA;
  }
</style>
