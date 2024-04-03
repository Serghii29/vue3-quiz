<script setup>
  import { ref } from 'vue';
  import Header from './components/Header.vue';
  import SingleQuestion from './components/SingleQuestion.vue';
  import MultipleQuestion from './components/MultipleQuestion.vue';
  import quiz from './data/quiz';

  const currentQuestionIndex = ref(0);

  const showNextQuestion = () => {
    if (currentQuestionIndex.value < quiz.length - 1) {
      currentQuestionIndex.value++;
    }
};
</script>

<template>
  <div class="wrapper">
    <Header />

    <div class="progress-bar"></div>

    <main class="main">
      <SingleQuestion
        v-if="quiz[currentQuestionIndex].type === 'single'"
        :question="quiz[currentQuestionIndex]"
        @next-question="showNextQuestion"
      />
      
      <MultipleQuestion
        v-else-if="quiz[currentQuestionIndex].type === 'multiple'"
        :question="quiz[currentQuestionIndex]"
        @next-question="showNextQuestion"
      />
    </main>
  </div>
</template>

<style scoped>
  .wrapper {
    width: 100%;
  }

  .progress-bar {
    width: 100%;
    height: 4px;

    background-image: linear-gradient(to right, #0000FF 50%, #D8D7E1 50%);
  }

  .main {
    padding: 32px 16px 0;
    background-color: #F8F7FA;
  }
</style>
