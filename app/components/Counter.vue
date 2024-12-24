<template>
    <div class="counter-container">
      <div 
        v-for="(item, index) in items" 
        :key="index"
        class="counter-circle"
        :style="{
          backgroundColor: item.color === 'red' ? 'var(--color-red)' : 'var(--color-black)'
        }"
      >
        <span class="counter-text" :class="{ whiteZero: item.number === 0 }">
          {{ item.number }}
        </span>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    props: {
      items: {
        type: Array,
        default: () => [
          { color: 'red', number: 0 },
          { color: 'black', number: 10 }
        ],
        validator(value) {
          return value.every(item => 
            typeof item.color === 'string' && typeof item.number === 'number'
          );
        }
      }
    }
  }
  </script>
  
  <style scoped>
  @import url('https://fonts.googleapis.com/css2?family=Anonymous+Pro&display=swap');
  
  :root {
    --font-main: 'Anonymous Pro', monospace;
    --color-red: #FF382C;   
    --color-black: #000000;
  
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
    display: inline-flex;
    height: 16px;
    padding: 0px 4px 0px 5px;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    flex-shrink: 0;
    border-radius: 100px; 
    font-family: var(--font-main);
    font-size: 12px;
    font-style: normal;
    font-weight: 700;
    line-height: normal;
  }
  
  .counter-text {
    position: relative;
    color: white; 
    text-align: center;
    font-family: "Anonymous Pro", monospace;
    font-size: 12px;
    font-style: normal;
    font-weight: 700;
    line-height: normal;
  }
  
  .counter-text.whiteZero {
    color: white; 
  }
  </style>