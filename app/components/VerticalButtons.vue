<template>
    <div class="button-column">

      <button class="custom-button white">пригласить друзей</button>
 
      <button class="custom-button red50">пригласить друзей</button>
  
      <button class="custom-button black">пригласить друзей</button>
    </div>
  </template>
  
  <script setup>
  </script>
  
  <style scoped>
  .button-column {
    display: flex;
    flex-direction: column; 
    gap: 16px; 
    align-items: center; 
    justify-content: flex-start; 
    width: 100%;
  }

  .custom-button {
    display: flex;
    width: 310px;
    height: 48px;
    padding: 8px 20px;
    justify-content: space-between;
    align-items: center;
    flex-shrink: 0;
    border-radius: 200px;
    font-family: inherit;
    font-size: 14px;
    font-weight: 700;
    cursor: pointer;
    transition: background-color 0.3s ease;
    border: none;
  }

  .white {
    background-color: var(--color-white, #FFFFFF);
    color: var(--color-black, #000000);
  }
  
  .white:hover {
    background-color: #f5f5f5;
  }
  
  .red50 {
    background-color: var(--color-red50, #FF382C80);
    color: var(--color-white, #FFFFFF);
  }
  
  .red50:hover {
    background-color: #FF382C;
  }
  
  .black {
    background-color: var(--color-black, #000000);
    color: var(--color-white, #FFFFFF);
  }
  
  .black:hover {
    background-color: #333333;
  }
  </style>