<template>
    <nav class="navbar">
      <ul>
        <li @click="selectMenu('peraturan')" :class="{ active: selectedMenu === 'peraturan' }">Peraturan</li>
        <li @click="selectMenu('hukuman')" :class="{ active: selectedMenu === 'hukuman' }">Hukuman</li>
      </ul>
    </nav>
  </template>
  
  <script setup>
  import { ref, defineEmits } from 'vue';
  
  const selectedMenu = ref('peraturan'); // Menu default
  const emit = defineEmits();
  
  const selectMenu = (menu) => {
    selectedMenu.value = menu;
    emit('update:menu', menu);
  };
  </script>
  
  <style scoped>
  .navbar {
    background-color: #333;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
    padding: 10px 20px;
    border-radius: 8px;
    width: 100%;
    max-width: 900px;
    margin-bottom: 20px;
    display: flex;
    justify-content: center;
  }
  
  ul {
    list-style-type: none;
    padding: 0;
    margin: 0;
    display: flex;
  }
  
  li {
    margin: 0 15px;
    padding: 10px 20px;
    cursor: pointer;
    color: #fff;
    transition: background-color 0.3s, color 0.3s;
  }
  
  li:hover {
    background-color: #9b1a1a;
    color: #fff;
    border-radius: 4px;
  }
  
  li.active {
    background-color: #9b1a1a;
    color: #fff;
    border-radius: 4px;
  }
  </style>
  