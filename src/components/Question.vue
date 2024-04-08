<script setup>
import {
  defineProps, defineComponent, ref,
} from 'vue';
import quiz from '../data/quiz';
import AnswersBlock from './Answers.vue';
import '../assets/question.css';

defineProps({
  question: {
    type: Object,
    default: () => ({}),
  },
});

defineComponent({
  name: 'QuizQuestion',
});

const currentQuestionIndex = ref(0);
const selectedAnswers = ref([]);

const showNextQuestion = () => {
  if (currentQuestionIndex.value < quiz.length - 1) {
    currentQuestionIndex.value += 1;
  }
};

const toggleAnswer = (answer) => {
  const index = selectedAnswers.value.indexOf(answer);
  if (index !== -1) {
    selectedAnswers.value.splice(index, 1);
  } else {
    selectedAnswers.value.push(answer);
  }
};

const handleNextQuestion = () => {
  if (selectedAnswers.value.length > 0) {
    showNextQuestion();
    selectedAnswers.value = [];
  }
};

</script>
<template>
  <article class="quiz">
    <h1 class="quiz__header">{{ quiz[currentQuestionIndex].title }}</h1>

    <p class="quiz__description">{{ quiz[currentQuestionIndex].description }}</p>

    <AnswersBlock
      :question="quiz[currentQuestionIndex]"
      @next-question="showNextQuestion"
      @toggle="toggleAnswer"
    />

    <button
      type="button"
      class="button"
      v-if="quiz[currentQuestionIndex].type === 'multiple'"
      :class="{ button__disabled: selectedAnswers.length === 0 }"
      @click="handleNextQuestion"
    >
      Continue
    </button>
  </article>
</template>
