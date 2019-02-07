<template>
  <div :class="show ? 'show' : 'hidden'">
    <slot></slot>
  </div>
</template>

<script>
  export default {
    name: 'Alert',
    props: {
      show: Boolean
    }
  }
</script>

<style scoped>
  .show, .hidden {
    box-sizing: border-box;
    padding: 0;
    background: green;
    color: white;
    transition: 300ms;
  }
  .hidden {
    opacity: 0;
  }
  .show {
    padding: 1rem;
    width: 100%;
    height: 100%;
    font-size: 1rem;
    opacity: 1;
  }
</style>