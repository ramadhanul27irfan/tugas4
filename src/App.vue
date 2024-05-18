<template>
  <div class="app-container">
    <h1 class="welcome-text">ATURAN BAR SEKARSA</h1>
    <Navbar @update:menu="selectedMenu = $event" />
    <div class="content">
      <Peraturan v-if="selectedMenu === 'peraturan'" />
      <Hukuman v-if="selectedMenu === 'hukuman'" />
    </div>
  </div>
</template>

<script>
import Navbar from './components/Navbar.vue';
import Peraturan from './components/Peraturan.vue';
import Hukuman from './components/Hukuman.vue';

export default {
  components: {
    Navbar,
    Peraturan,
    Hukuman,
  },
  data() {
    return {
      selectedMenu: 'peraturan', // Default menu yang dipilih
    };
  },
};
</script>

<style scoped>
/* Global styles */
.app-container {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  min-height: 100vh;
  font-family: 'Roboto', sans-serif;
  color: #333;
  background-image: url(components/image/bgd.avif);
  background-color: #f7f1e3; /* Warna putih krem yang hangat */
}

.welcome-text {
  font-size: 2rem;
  margin-bottom: 20px;
  text-align: center;
  color: #4a312c; /* Warna coklat muda */
  background-color: #f3d9c4; /* Warna krem yang lebih terang */
  padding: 15px;
  border-radius: 8px;
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
}

.content {
  background-color: #faf3e0; /* Warna kuning krem */
  padding: 20px;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
  border-radius: 8px;
  width: 100%;
  max-width: 900px;
  margin-top: 20px;
}

/* Navbar styles */
.navbar {
  background-color: #4a312c; /* Warna coklat muda */
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
  color: #f7f1e3; /* Warna putih krem */
  transition: background-color 0.3s, color 0.3s;
}

li:hover {
  background-color: #7a5533; /* Warna coklat kemerahan */
  color: #f7f1e3; /* Warna putih krem */
  border-radius: 4px;
}

li.active {
  background-color: #7a5533; /* Warna coklat kemerahan */
  color: #f7f1e3; /* Warna putih krem */
  border-radius: 4px;
}

</style>
