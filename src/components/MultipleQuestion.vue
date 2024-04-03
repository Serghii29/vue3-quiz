<template>
  <section class="quiz">
    <h1 class="quiz__header">{{ question.title }}</h1>

    <p class="quiz__description">{{ question.description }}</p>

    <div class="quiz__question-wrapper" v-for="answer in question.answers" :key="answer.text">
      <label class="question">
        <input
          type="checkbox"
          name="question"
          value="Text 3"
          class="question__input"
        />

        <span class="question__custom-checbox"> </span>

        <p class="question__icon">{{ answer.smile }}</p>

        <p class="question__text">{{ answer.text }}</p>
      </label>
    </div>

    <button type="button" class="button">Continue</button>
  </section>
</template>

<script setup>
  import '../assets/question.css';
  import { defineProps, defineComponent } from 'vue';

  const props = defineProps({
    question: {
      type: Object,
    }
  });

  defineComponent({
    name: 'MultipleQuestion',
  })
</script>
