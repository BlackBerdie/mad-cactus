<template>
    <div class="counter-container">
      <div 
        v-for="(item, index) in items" 
        :key="index"
        class="counter-circle"
        :style="{ backgroundColor: item.color }"
      >
        <span class="counter-text" :class="{ crossed: item.number === 0 }">
          {{ item.number }}
        </span>
      </div>
    </div>
  </template>
  
  <script setup>
  defineProps({
    items: {
      type: Array,
      default: () => [
        { color: '#000000', number: 0 },
        { color: '#FF4444', number: 10 }
      ],
      validator(value) {
        return value.every(item => 
          typeof item.color === 'string' && 
          typeof item.number === 'number'
        );
      }
    }
  });
  </script>
  
  <style scoped>
  @import url('https://fonts.googleapis.com/css2?family=Anonymous+Pro&display=swap');
  
  :root {
    --font-main: 'Anonymous Pro', monospace;
  }
  
  .counter-container {
    position: relative;
    padding: 20px;
    border: 2px dashed #8A2BE2;
    border-radius: 16px;
    display: flex;
    flex-direction: column;
    gap: 20px;
    align-items: center;
    background-color: #2A2A2A;
    min-width: 100px;
  }
  
  .counter-circle {
    width: 60px;
    height: 60px;
    border-radius: 50%;
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 24px;
    color: white;
    font-weight: bold;
    transition: all 0.3s ease;
    position: relative;
    font-family: var(--font-main);
  }
  
  .counter-circle:hover {
    transform: scale(1.1);
    cursor: pointer;
  }
  
  .counter-text {
    position: relative;
    color: white; 
  }
  
  .counter-text.crossed {
    text-decoration: line-through;
    color: red; 
  }
  
  .counter-text:not(.crossed) {
    color: white; 
  }
  </style>