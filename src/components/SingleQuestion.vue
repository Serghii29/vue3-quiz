<script setup>
  import '../assets/question.css';

  import { defineProps, defineComponent } from 'vue';

  const props = defineProps({
    question: {
      type: Object,
    }
  });

  defineComponent({
    name: 'SingleQuestion',
  })

</script>

<template>
  <section class="quiz">
    <h1 class="quiz__header">{{ question.title }}</h1>

    <p class="quiz__description">{{ question.description }}</p>

    <div class="quiz__question-wrapper">
      <button class="question" v-for="answer in question.answers" :key="answer.text">
        <p class="question__icon">{{ answer.smile }}</p>
        <p class="question__text">{{ answer.text }}</p>
      </button>
    </div>
  </section>
</template>
