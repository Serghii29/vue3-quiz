<template>
  <section class="quiz">
    <h1 class="quiz__header">Heading</h1>

    <p class="quiz__description">Choose all that apply</p>

    <div class="quiz__question-wrapper">
      <button class="question">
        <p class="question__icon">🫣</p>
        <p class="question__text">Text 3</p>
      </button>

      <button class="question">
        <p class="question__icon">🫣</p>
        <p class="question__text">Text 3</p>
      </button>

      <button class="question">
        <p class="question__icon">🫣</p>
        <p class="question__text">Text 3</p>
      </button>
    </div>
  </section>
</template>

<script>
  import '../assets/question.css';

  export default {
    name: 'SingleQuestion'
  }
</script>
