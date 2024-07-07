<template>
  <div class="typing-text">
    <span>{{ displayText }}</span>
    <span v-if="showCursor" class="cursor">|</span>
  </div>
</template>

<script setup>
import { ref, onMounted } from 'vue';

const props = defineProps({
  text: {
    type: String,
    required: true,
  },
});

const displayText = ref('');
const showCursor = ref(true);

const typeText = () => {
  let index = 0;
  const interval = setInterval(() => {
    if (index < props.text.length) {
      displayText.value += props.text[index];
      index++;
    } else {
      clearInterval(interval);
    }
  }, 100);
};

onMounted(() => {
  typeText();
  setInterval(() => {
    showCursor.value = !showCursor.value;
  }, 500);
});
</script>

<style scoped>
.cursor {
  display: inline-block;
  width: 1px;
  background-color: none;
}
</style>