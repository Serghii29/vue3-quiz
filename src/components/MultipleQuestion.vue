<script setup>
  import { defineProps, defineComponent, defineEmits, ref } from 'vue';
  import '../assets/question.css';

  const props = defineProps({
    question: {
      type: Object,
    }
  });

  defineComponent({
    name: 'MultipleQuestion',
  });

  const emit = defineEmits(['next-question']);

  const selectedAnswers = ref([]);

  const toggleAnswer = (answer) => {
    const index = selectedAnswers.value.indexOf(answer);
    if (index !== -1) {
      selectedAnswers.value.splice(index, 1);
    } else {
      selectedAnswers.value.push(answer);
    }
    console.log(selectedAnswers);
  };

  const handleNextQuestion = () => {
    if (selectedAnswers.value.length > 0) {
      emit('next-question');
      selectedAnswers.value = [];
    }
  };
</script>

<template>
  <section class="quiz">
    <h1 class="quiz__header">{{ question.title }}</h1>

    <p class="quiz__description">{{ question.description }}</p>

    <div class="quiz__question-wrapper" v-for="answer in question.answers" :key="answer.text">
      <label class="question">
        <input
          type="checkbox"
          name="question"
          :value="answer.text"
          class="question__input"
          @change="toggleAnswer(answer)"
        />

        <span class="question__custom-checbox"> </span>

        <p class="question__icon">{{ answer.smile }}</p>

        <p class="question__text">{{ answer.text }}</p>
      </label>
    </div>

    <button
      type="button"
      class="button"
      :class="{ 'button__disabled': selectedAnswers.length === 0 }"
      @click="handleNextQuestion"
    >
      Continue
  </button>
  </section>
</template>
