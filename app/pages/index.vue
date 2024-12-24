<template>
  <div>
    <h1>Добро пожаловать в Nuxt 3!</h1>
    <FriendsIcon :count="5" :onClick="handleClick" />
  </div>
</template>

<script setup>
import FriendsIcon from '~/components/FriendsIcon.vue';

const handleClick = () => {
  alert('Кнопка была нажата!');
};
</script>