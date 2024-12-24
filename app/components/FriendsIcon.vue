<template>
    <div>
      <div
        class="button-icon top"
        :class="{ clickable: !!onClick }"
        @click="handleClick"
      >
        <div class="icon">
          <img src="@/assets/icons/friends.svg" alt="Friends Icon" />
        </div>
        <span v-if="count !== undefined" class="counter">{{ count }}</span>
      </div>
  
      
      <div
        class="button-icon bottom"
        :class="{ clickable: !!onClick }"
        @click="handleClick"
      >
        <div class="icon">
        
          <img src="@/assets/icons/friends.svg" alt="Friends Icon" />
        </div>
        <span v-if="count !== undefined" class="counter">{{ count }}</span>
      </div>
    </div>
  </template>
  
  <script setup>
  defineProps({
    count: {
      type: Number,
      default: undefined,
    },
    onClick: {
      type: Function,
      default: null,
    },
  });
  
  const handleClick = () => {
    if (props.onClick) {
      props.onClick();
    }
  };
  </script>
  
  <style scoped>
  .button-icon {
    display: inline-flex;
    padding: 8px;
    align-items: center;
    gap: 8px;
    border-radius: 200px;
    background: #fff;
    position: relative;
    cursor: default;
  }
  
  .button-icon.clickable {
    cursor: pointer;
  }
  
  .icon {
    display: flex;
    align-items: center;
  }
  
  .counter {
    position: absolute;
    top: -5px;
    right: -5px;
    background: #ff4136;
    color: #fff;
    border-radius: 50%;
    padding: 4px 6px;
    font-size: 12px;
    font-weight: bold;
  }

  .button-icon.top {
    margin-bottom: 16px; 
  }
  
  .button-icon.bottom {
    margin-top: 16px; 
  }
  </style>