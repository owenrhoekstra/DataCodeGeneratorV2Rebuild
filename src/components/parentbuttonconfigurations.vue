<script setup lang="ts">
import Selectablebuttonchild from './selectablebuttonchild.vue'
import ClickableButtonChild from './clickablebuttonchild.vue'
import { ref } from "vue"
const selected = ref<string | null>(null)

const twoDbuttons = [
  { label: 'QR', value: 'qr' },
  { label: 'Micro QR', value: 'microqr' },
  { label: 'Data Matrix', value: 'datamatrix' },
  { label: 'PDF-417', value: 'pdf417' },
  { label: 'Aztec', value: 'aztec' },
  { label: 'Maxi Code', value: 'maxicode' },
]

const oneDbuttons = [
    { label: 'UPC-A', value: 'upca' },
    { label: 'UPC-E', value: 'upce' },
    { label: 'EAN-14', value: 'ean14' },
    { label: 'EAN-13', value: 'ean13' },
    { label: 'EAN-8', value: 'ean8' },
    { label: 'Code 128', value: 'code128' },
    { label: 'Code 93', value: 'code93' },
    { label: 'ITF-14', value: 'itf14' },
]

function handleSelect(v: string) {
  selected.value = v
}

function handleClear() {
  selected.value = null
}
</script>

<template>
  <div class="button-list">
    <p>2-D Codes: </p>
    <Selectablebuttonchild
        v-for="b in twoDbuttons"
        :key="b.value"
        :label="b.label"
        :value="b.value"
        :selected="selected"
        @select="handleSelect"
    />
  </div>
  <div class="button-list">
    <p>1-D Codes: </p>
    <Selectablebuttonchild
        v-for="b in oneDbuttons"
        :key="b.value"
        :label="b.label"
        :value="b.value"
        :selected="selected"
        @select="handleSelect"
    />
  </div>
  <ClickableButtonChild
      label="Clear Selection"
      @click="handleClear"
      class="clearbutton"
  />
</template>

<style scoped>
.button-list {
  display: flex;
  flex-wrap: wrap;
  gap: 10px;
  padding: 10px;
  justify-content: center;
  font-family: "Courier New", Courier, monospace;
  font-weight: bold;
}
.clearbutton {
  margin-top: 20px;
}
</style>