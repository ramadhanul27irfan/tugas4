<template>
  <div class="hukuman-container">
    <h1>Daftar Hukuman</h1>
    <ul>
      <li v-for="(hukuman, index) in hukumanList" :key="index">
        {{ hukuman }}
      </li>
    </ul>
  </div>
</template>

<script setup>
import { ref, onMounted } from 'vue';

const hukumanList = ref([]);

const fetchHukuman = async () => {
  const data = [
  '1. Keterlambatan akan di cek di sistem setiap harinya. Setiap keterlambatan akan diakumulasikan perminggunya, batas akumulasi keterlambatan hanya 4jam perminggu lebih dari 4jam akan dikenakan denda sebesar 25k.  mengganti jamnya akan dikonfirmasi hari apa yang diinginkan kecuali dihari libur. Untuk menggantinya anggota harus datang lebih cepat berdasarkan jumlah akumulasi keterlambatannya, jika telat juga akan didenda permenitnya 2k.',
  '2. izin mendadak tidak dapat hadir akan dikenakan denda/pemotongan gaji sebesar 25k dan pemotongan gaji',
  '3. Izin tanpa memberikan bukti akan didenda 10k',
  '4. untuk poin nomor 5 ketika dilanggar akan didenda/pemotongan gaji sebesar 10k .Untuk penggunaan apron hanya wajib disaat bekerja',
  '5. Cup yang salah membuat nama / pesanan akan dikenakan denda sebesar 2k percup',
  '6. Ketahuan mengambil jatah minum selain yg dijelaskan Dan ketahuan mengambil lebih dari 1 sehari akan dihitung bayar',
  '7. Point 10,13, 14, 16,17 ketahuan melanggar akan di denda/pemotangan gaji 10k/pershift .contoh 2 orang shift maka 5k/orang (Untuk poin 14 kondisonal, jika terlihat kotor sekali baru dikatakan melanggar pointnya)',
];
  hukumanList.value = data;
};

onMounted(() => {
  fetchHukuman();
});
</script>

<style scoped>
.hukuman-container {
  max-width: 600px;
  margin: 0 auto;
  padding: 20px;
  background-color: #f9f9f9;
  border-radius: 8px;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
}

h1 {
  text-align: center;
  margin-bottom: 20px;
  color: #333;
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  background-color: #fff;
  margin: 10px 0;
  padding: 15px;
  border-radius: 4px;
  box-shadow: 0 1px 3px rgba(0, 0, 0, 0.1);
}
</style>
