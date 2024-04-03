<script setup>
  import { defineProps, defineComponent, defineEmits } from 'vue';
  import '../assets/question.css';

  const props = defineProps({
    question: {
      type: Object,
    }
  });

  defineComponent({
    name: 'SingleQuestion',
  });

  const emit = defineEmits(['next-question']);

  const handleNextQuestion = () => {
    emit('next-question');
  };

</script>

<template>
  <section class="quiz">
    <h1 class="quiz__header">{{ question.title }}</h1>

    <p class="quiz__description">{{ question.description }}</p>

    <div class="quiz__question-wrapper">
      <button
        type="button"
        class="question"
        v-for="answer in question.answers"
        :key="answer.text"
        @click="handleNextQuestion"
      >
        <p class="question__icon">{{ answer.smile }}</p>
        <p class="question__text">{{ answer.text }}</p>
      </button>
    </div>
  </section>
</template>
