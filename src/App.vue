<script setup>
import NotififcationMsg from './components/NotififcationMsg.vue';
</script>

<template>
  <h1 style="text-align: center; margin-bottom: 15px;">Notification Center</h1>
  <NotififcationMsg :type="'error'"> Hello</NotififcationMsg>
  <NotififcationMsg :type="'success'"> Hello</NotififcationMsg>
  
</template>
