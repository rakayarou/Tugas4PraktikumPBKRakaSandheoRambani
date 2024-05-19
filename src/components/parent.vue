<template>
    <div class="parent">
      <h2>Parent Component</h2>
      <p>Data from Child: {{ childData }}</p>
      <ChildOne @data-from-child="handleDataFromChild" />
      <ChildTwo @data-from-child="handleDataFromChild" />
    </div>
  </template>
  
  <script>
  import { ref } from 'vue';
  import ChildOne from './childone.vue';
  import ChildTwo from './childetwo.vue';
  
  export default {
    name: 'parent',
    components: {
      ChildOne,
      ChildTwo,
    },
    setup() {
      const childData = ref('');
  
      const handleDataFromChild = (data) => {
        childData.value = data;
      };
  
      return {
        childData,
        handleDataFromChild,
      };
    },
  };
  </script>
  
  <style scoped>
  .parent {
    padding: 20px;
    border: 2px solid #ddd;
    margin: 20px;
    text-align: center;
    background-color: #000000;
  }
  </style>