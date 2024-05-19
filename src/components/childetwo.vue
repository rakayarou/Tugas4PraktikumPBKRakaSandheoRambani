<template>
    <div class="child">
      <h3>Child Two</h3>
      <button @click="sendData">Klik Tombol Ini</button>
    </div>
  </template>
  
  <script>
  export default {
    name: 'childetwo',
    emits: ['data-from-child'],
    setup(props, { emit }) {
      const sendData = () => {
        emit('data-from-child', 'Data from child two');
      };
  
      return {
        sendData,
      };
    },
  };
  </script>
  
  <style scoped>
  .child {
    border: 1px solid #d21b45;
    padding: 10px;
    margin: 10px;
    text-align: center;
  }
  button {
    background-color: #ec114f;
    color: rgb(0, 0, 0); 
    border: none;
    padding: 10px 20px;
    cursor: pointer;
  }
  button:hover {
    background-color: #e4247e;
  }
  </style>
  