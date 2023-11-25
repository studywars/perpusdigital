<template>
  <div class="row body pt-5">
    <div class="col text-center py-3 text-light">
      <h2>Riwayat Pengunjung Perpustakaan</h2>
      <h1>SMKN 4 Tasikmalaya</h1>
      <div class="table-responsive py-3">
        <NuxtLink to="/tambah" class="btn btn-primary">Isi Buku Kunjungan</NuxtLink>
        <table>
          <thead>
            <tr>
              <th>No</th>
              <th>Nama</th>
              <th>Anggota</th>
              <th>Kelas</th>
              <th>Keperluan</th>
              <th>Tanggal</th>
            </tr>
          </thead>
          <tbody>
            <tr v-for="item in items" :key="item.id">
              <td>{{ item.id }}</td>
              <td>{{ item.nama }}</td>
              <td>{{ item.anggota }}</td>
              <td>{{ item.kelas }}</td>
              <td>{{ item.keperluan }}</td>
              <td>{{ item.tanggal }}</td>
            </tr>
          </tbody>
        </table>
      </div>
    </div>
    <div class="div-col-lg">
      <select name="" id=""></select>
    </div>
  </div>
</template>

<script setup>
useHead({ title: "Pengunjung - Aplikasi Buku Kunjungan" });
import { onMounted, ref } from "vue";

const supabase = useSupabaseClient();
const items = ref([]);

async function ambilData() {
  const { data, error } = await supabase.from("perpusDigital").select().order("id", { ascending: false });
  // if (error) throw error;
  if (data) items.value = data;
}

onMounted(() => {
  ambilData();
});
</script>

<style scoped>
@import url("https://fonts.googleapis.com/css2?family=Libre+Baskerville:wght@700&family=Poppins:wght@400;500;900&display=swap");
@import url("https://fonts.googleapis.com/css2?family=Libre+Baskerville:wght@700&family=Poppins:wght@400;500;900&display=swap");
@import url("https://fonts.googleapis.com/css2?family=Libre+Baskerville:wght@700&family=Poppins:wght@300;400;500;900&display=swap");

h3 {
  font-family: "Libre Baskerville", serif;
  font-family: "Poppins", sans-serif;
}

h1 {
  font-family: "Libre Baskerville", serif;
  font-family: "Poppins", sans-serif;
}

th {
  font-family: "Libre Baskerville", serif;
  font-family: "Poppins", sans-serif;
}

td {
  font-family: "Libre Baskerville", serif;
  font-family: "Poppins", sans-serif;
}

.btn {
  font-family: "Libre Baskerville", serif;
  font-family: "Poppins", sans-serif;
}
</style>
