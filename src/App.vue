
<template>
    <div id="app">
    <p :class="{ 'highlight': isHighlighted }" :style="{ 'font-weight': isBold ? 'bold' : 'normal' }">Ini adalah teks dengan class dan style bindings</p>
    <input type="text" v-model="inputText" @input="onInput">
    <p>Data input: {{ inputText }}</p>
  </div>
  </template>

<script setup>
    import { ref } from 'vue'

    const inputText = ref('');
    const isHighlighted = ref(false);
    const isBold = ref(false);
    const Upercase = ref(false)

    const onInput = () => {
        isHighlighted.value = inputText.value.length > 5;
        isBold.value = inputText.value.length > 10;
    };
</script>

<style scoped>

</style>
