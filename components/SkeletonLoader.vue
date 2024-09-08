<!-- components/SkeletonLoader.vue -->
<template>
    <div class="skeleton-loader" v-for="(i, index) in blocks" :key="index">
      <!-- Customize your skeleton loader styles here -->
      <div class="skeleton-loader__header"></div>
      <div class="skeleton-loader__content">
        <div class="skeleton-loader__line"></div>
        <div class="skeleton-loader__line"></div>
        <div class="skeleton-loader__line"></div>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    name: 'SkeletonLoader',
    props:{
      blocks: Number,
    }
  }
  </script>
  
<style scoped>
  .skeleton-loader {
    background-color: transparent; /* Set background to transparent */
    border-radius: 4px;
    padding: 16px;
  }
  
  .skeleton-loader__header {
    height: 20px;
    background: linear-gradient(90deg, rgba(255, 255, 255, 0.2) 25%, rgba(255, 255, 255, 0.1) 50%, rgba(255, 255, 255, 0.2) 75%);
    background-size: 200% 100%;
    animation: shine 1.5s infinite;
    margin-bottom: 10px;
    border-radius: 4px;
  }
  
  .skeleton-loader__line {
    height: 12px;
    background: linear-gradient(90deg, rgba(255, 255, 255, 0.2) 25%, rgba(255, 255, 255, 0.1) 50%, rgba(255, 255, 255, 0.2) 75%);
    background-size: 200% 100%;
    animation: shine 1.5s infinite;
    margin-bottom: 8px;
    border-radius: 4px;
  }
  
  .skeleton-loader__line:last-child {
    margin-bottom: 0;
  }
  
  @keyframes shine {
    0% {
      background-position: -200% 0;
    }
    100% {
      background-position: 200% 0;
    }
  }
</style>