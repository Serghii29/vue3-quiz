<script setup>
// import HelloWorld from './components/HelloWorld.vue'
// import TheWelcome from './components/TheWelcome.vue'
</script>

<template>
  <!-- <header>
    <img alt="Vue logo" class="logo" src="./assets/logo.svg" width="125" height="125" />

    <div class="wrapper">
      <HelloWorld msg="You did it!" />
    </div>
  </header>

  <main>
    <TheWelcome />
  </main> -->

  <div class="wrapper">
    <header class="header">
      <div>
        <button class="header__back">
          <img src="./assets/left.png" alt="icon back" width="14" height="10">
        </button>
      </div>

      <img src="./assets/logo.png" alt="logo">

      <p class="header__title">1/26</p>
    </header>

    <div class="progress-bar"></div>

    <main class="main">
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
    </main>
  </div>
</template>

<style scoped>
  .wrapper {
    width: 100%;
  }

  .header {
    display: flex;
    align-items: center;
    justify-content: space-between;
    width: 100%;
    padding: 8px 16px;
  }

  .header__back {
    border: none;
    background-color: #fff;
    cursor: pointer;
  }

  .header__title {
    font-weight: 700;
    font-size: 12px;
    line-height: 28px;
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

  .quiz {
    display: flex;
    flex-direction: column;
    align-items: center;
    width: 100%;
  }

  .quiz__header {
    font-weight: 700;
    font-size: 22px;
    line-height: 127%;
    margin-bottom: 10px;
  }

  .quiz__description {
    color: #5A5867;
    line-height: 150%;
    margin-bottom: 31px;
  }

  .quiz__question-wrapper {
    width: 100%;
    display: flex;
    flex-direction: column;
    gap: 8px;
    margin-bottom: 24px;
  }

  .question {
    display: flex;
    align-items: center;
    gap: 16px;
    width: 100%;
    padding: 24px 16px;
    border-radius: 12px;
    border: 1px solid #EAE9F0;
    background-color: #fff;
    cursor: pointer;
  }

  .question__icon {
    font-size: 32px;
  }

  .question__text {
    font-size: 16px;
    line-height: 150%;
  }

  .question__input {
    position: absolute;
    width: 0;
    height: 0;
    opacity: 0;
  }

  .question__custom-checbox {
    position: relative;
    float: right;
    width: 16px;
    height: 16px;
    border-radius: 6px;
    border: 1px solid #D8D7E1;
    vertical-align: sub;
    cursor: pointer;
  }

  .question__custom-checbox::before {
    content: '';

    display: inline-block;
    width: 6px;
    height: 6px;

    background-image: url('./assets/done.svg');
    background-size: contain;
    background-repeat: no-repeat;

    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%) scale(0);
    margin-top: 1px;
    transition: 0.5s ease-in;
  }

  .question__input:checked + .question__custom-checbox::before {
    transform: translate(-50%, -50%) scale(1);
  }

  .question__input:checked + .question__custom-checbox {
    background-color: #806FFB;
  }

  .button {
    width: 100%;
    color: #fff;
    background-color: #806FFB;
    padding: 24px 0;
    border-radius: 12px;
    border: none;
    font-size: 20px;
    cursor: pointer;
  }
</style>
