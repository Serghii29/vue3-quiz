<script setup>
  import Header from './components/Header.vue';
  import SingleQuestion from './components/SingleQuestion.vue';
  import MultipleQuestion from './components/MultipleQuestion.vue';
</script>

<template>
  <div class="wrapper">
    <Header />

    <div class="progress-bar"></div>

    <main class="main">
      <SingleQuestion />

      <MultipleQuestion />
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
