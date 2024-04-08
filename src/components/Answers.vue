<script setup>
import {
  defineProps, defineComponent, defineEmits,
} from 'vue';
import '../assets/question.css';

defineProps({
  question: {
    type: Object,
    default: () => ({}),
  },
});

defineComponent({
  name: 'AnswersBlock',
});

const emits = defineEmits(['next-question', 'toggle']);
</script>

<template>
  <div class="quiz__question-wrapper">
    <label
      v-for="answer in question.answers"
      class="question"
      :key="answer.text"
    >
      <input
        :type="question.type === 'multiple' ? 'checkbox' : 'button'"
        name="question"
        class="question__input"
        @click="question.type === 'single' ? emits('next-question') : emits('toggle', answer)"
      />

      <span v-if="question.type === 'multiple'" class="question__custom-checbox" />

      <p class="question__icon">{{ answer.smile }}</p>

      <p>{{ answer.text }}</p>
    </label>
  </div>
</template>
