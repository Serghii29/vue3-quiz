<script setup>
import { defineComponent } from 'vue';

defineComponent({
  name: 'AppHeader',
});
</script>

<template>
  <header class="header">
    <div>
      <button type="button" class="header__back">
        <img src="../assets/left.png" alt="icon back" width="14" height="10">
      </button>
    </div>

    <img src="../assets/logo.png" alt="logo">

    <p class="header__title">1/26</p>
  </header>
</template>

<style scoped>
.header {
    display: flex;
    align-items: center;
    justify-content: space-between;
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
    line-height: 18px;
  }
</style>
