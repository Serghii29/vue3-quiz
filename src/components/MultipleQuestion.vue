<template>
  <section class="quiz">
    <h1 class="quiz__header">Heading</h1>

    <p class="quiz__description">Choose all that apply</p>

    <div class="quiz__question-wrapper">
      <label class="question">
        <input
          type="checkbox"
          name="question"
          value="Text 3"
          class="question__input"
        />

        <span class="question__custom-checbox"> </span>

        <p class="question__icon">🫣</p>

        <p class="question__text">Text 3</p>
      </label>
    </div>

    <button type="button" class="button">Continue</button>
  </section>
</template>

<script>
  import '../assets/question.css';

  export default {
    name: 'MultipleQuestion'
  }
</script>
