<template>
  <div class="button-wrapper">
    <button :class="['custom-button', variant]" :disabled="disabled">
      <span class="button-text">
        <slot>{{ text }}</slot>
      </span>
    </button>
  </div>
</template>

<script setup>
defineProps({
  variant: {
    type: String,
    default: 'red50', 
    validator: value => ['white', 'red50', 'black'].includes(value)
  },
  text: {
    type: String,
    default: 'С тобой поменялись очками' 
  },
  disabled: {
    type: Boolean,
    default: false
  }
});
</script>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Anonymous+Pro&display=swap');

:root {
  --font-main: 'Anonymous Pro', monospace;
  --color-red: #FF382C;
  --color-black: #000000;
  --color-white: #FFFFFF;
  --color-red50: #FF382C80;
}


.button-wrapper {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh; 
}

.custom-button {
  display: flex;
  width: 310px;
  height: 48px;
  padding: 12px 16px;
  justify-content: center;
  align-items: center;
  flex-shrink: 0;
  border-radius: 12px;
  font-family: var(--font-main);
  font-size: 14px;
  font-weight: 700;
  cursor: pointer;
  transition: background-color 0.3s ease;
  border: none;
}

.custom-button:disabled {
  opacity: 0.6;
  cursor: not-allowed;
}

.white {
  background-color: var(--color-white);
  color: var(--color-black);
}

.white:hover {
  background-color: #f5f5f5;
}

.red50 {
  background-color: var(--color-red50);  
  color: var(--color-black);
}

.red50:hover {
  background-color: var(--color-red); 
}

.black {
  background-color: var(--color-black);
  color: var(--color-white);
}

.black:hover {
  background-color: #333333;
}

.button-text {
  display: block;
}
</style>