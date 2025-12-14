<script setup>
import Parentbuttonconfigurations from './components/parentbuttonconfigurations.vue'
</script>

<template>
  <Parentbuttonconfigurations />
  <form name="Requests" netlify>
    <p>
      <label>Errors<input type="text" name="error" /></label>
    </p>
    <p>
    <label>Feature Requests<input type="text" name="features" /></label>
    </p>
    <p>
      <label>Other Comments<input type="text" name="comments" /></label>
    </p>
    <p>
      <button type="submit">Send</button>
    </p>
  </form>
</template>

<style scoped>
/* keep whatever styles you actually care about */
</style>