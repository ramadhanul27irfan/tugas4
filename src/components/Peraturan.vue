<template>
  <div class="peraturan-container">
    <h1>Daftar Peraturan</h1>
    <ul>
      <li v-for="(peraturan, index) in peraturanList" :key="index">
        {{ peraturan }}
      </li>
    </ul>
  </div>
</template>

<script setup>
import { ref, onMounted } from 'vue';

const peraturanList = ref([]);

const fetchPeraturan = async () => {
  const data = [
    '1. Datang tepat waktu jam 08.00/16.00 wib.',
    '2. Berpakaian rapi dan memakai wangi wangian, Menggunakan sepatu tidak boleh sendal apapun.',
    '3. Menjaga kerahasiaan bahan baku dengan membuang label kemasan. ',
    '4. Mengikuti shif yang telah dibuat. ',
    '5. Saat Bekerja wajib menggunakan Apron dan ID Card. ',
    '6. Izin di perbolehkan minimal h-1, dan untuk izin harus meberikan bukti yg jelas,seperti bukti chat atau foto. untuk izin bisa langsung hubungi headbar',
    '7. Ketidak hadiran yang di cover rekan kerja (cuti) maka gaji diberikan ke rekan yg mengcover.',
    '8. Tidak boleh mengambil jatah minuman selain lemon tea, lychetea.',
    '9. Pesanan diindor wajib diantar, kecuali saat kondisi krusial seperti malming.',
    '10. Saat mengantar pesanan wajib menggunakan nampan.',
    '11. Wajib mencatat nama dan pesanan customer di cup (tidak boleh hanya 1cup yg mewakli pesanan lain).',
    '12. Jika ada barang bar yg hilang atau rusak wajib diganti.',
    '13. Wajib memperhatikan kualitas es kristal, diharapkan menjaga suhu showcase es dengan menutup kembali setelah pemakaian.',
    '14. Setelah membuat minuman wajib menjaga kebersihan area bar, terutama meja bar.',
    '15. Jika ada pesanan yang salah, shift hari itu harus bertanggung jawab dengan mengganti pesanan tersebut.',
    '16. Penggunaan steam hanya digunakan untuk pesanan HOT.',
    '17. Shift pagi wajib menyetok esspresoo minimal 2liter, jelly, aren,dll setiap harinya.',
    '18. Shift pagi wajib update stok bahan baku.',
    '19. Shift sore wajib membuat stok minuman, minimal kopi 20cup dan non coffee masing-masing 10cup.',
    '20. Peralatan yang berhubungan dengan coffee seperti botol stok esspresso,saringan, dan portafilter tidak boleh dicuci dengan sunlight.',
    '21. Kain lap khusus (berwarna coklat) kopi tidak boleh digunakan dengan hal yang lain.',
  ];
  peraturanList.value = data;
};

onMounted(() => {
  fetchPeraturan();
});
</script>

<style scoped>
.peraturan-container {
  max-width: 600px;
  margin: 0 auto;
  padding: 20px;
  background-color: #fff;
  border-radius: 8px;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
}

h1 {
  text-align: center;
  margin-bottom: 20px;
  color: #000000; 
  font-weight: bold;
  text-transform: uppercase;
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  background-color: #f9f9f9; /* Warna latar belakang yang bersih */
  margin: 10px 0;
  padding: 15px;
  border-radius: 4px;
  box-shadow: 0 1px 3px rgba(0, 0, 0, 0.1); /* Bayangan halus untuk memberikan dimensi */
  color: #333; /* Warna teks yang mudah dibaca */
  font-weight: 500; /* Ketebalan teks */
}
</style>
