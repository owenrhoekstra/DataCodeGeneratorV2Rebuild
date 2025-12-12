<script setup lang="ts">
const { label } = defineProps<{ label: string }>()

const emit = defineEmits<{
  (e: 'click'): void
}>()

function handleClick() {
  emit('click')
}
</script>

<template>
  <button @click="handleClick">
    {{ label }}
  </button>
</template>

<style scoped>
button {
  font-family: "Courier New", Courier, monospace;
  font-weight: bold;
}
</style>