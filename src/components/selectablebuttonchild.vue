<script setup lang="ts">
const props = defineProps<{
  label: string
  value: string
  selected: string | null
}>()

const emit = defineEmits<{
(e: 'select', value: string): void
}>()

function handleClick() {
  emit('select', props.value)
}

</script>

<template>
<button @click="handleClick" :class="{ active: props.selected === props.value }">
  {{ label }}
</button>
</template>

<style scoped>
button {
  font-family: "Courier New", Courier, monospace;
  font-weight: bold;
}
button.active {
  background-color: #ffcc00;
  color: #000;
}
</style>