<template>
  <div class="container bg-color">
    <div class="bee text-center">
      <h1>Isi Data Kunjungan</h1>
    </div>
    <form @submit.prevent="handleSubmit()">
      <div class="mb-3 row">
        <label for="text" class="col-sm-2 col-form-label">Nama</label>
        <input v-model="Nama" type="text" class="form-control" id="exampleFormControlInput1" placeholder="Nama" />
      </div>
      <div class="mb-3 row">
        <label for="text" class="col-sm-2 col-form-label">Keanggotaan</label>
        <select v-model="Keanggotaan" class="form-control form-select">
          <option value="">Pilih Kategori Anggota</option>
          <option value="Siswa">Siswa</option>
          <option value="Guru">Guru</option>
          <option value="Staff">Staff</option>
        </select>
      </div>
      <div v-if="Keanggotaan == 'Siswa'" class="mb-3">
        <label for="text" class="col-sm-2 col-form-label">Tingkat</label>
        <select v-model="Tingkatan">
          <option value="">Pilih Tingkat</option>
          <option value="10">10</option>
          <option value="11">11</option>
          <option value="12">12</option>
        </select>
        <label for="text" class="col-sm-2 col-form-label">Jurusan</label>
        <select v-model="Jurusan">
          <option value="">Pilih Jurusan</option>
          <option value="PPLG">PPLG</option>
          <option value="TBSM">TBSM</option>
          <option value="TJKT">TJKT</option>
          <option value="DKV">DKV</option>
          <option value="TOI">TOI</option>
        </select>
        <label for="text" class="col-sm-2 col-form-label">Kelas</label>
        <select v-model="Kelas">
          <option value="">Pilih Kelas</option>
          <option value="1">1</option>
          <option value="2">2</option>
          <option value="3">3</option>
          <option value="4">4</option>
        </select>
      </div>
      <div class="mb-3">
        <label for="exampleFormControlTextarea1" class="form-label">Keperluan</label>
        <textarea v-model="Keperluan" class="form-control" id="exampleFormControlTextarea1" rows="3"></textarea>
      </div>
      <div>
        <button class="btn btn-biru btn-sm float-right" type="submit">Kirim</button>
      </div>
    </form>
  </div>
</template>

<script setup>
const supabase = useSupabaseClient();
const Nama = ref("");
const Keanggotaan = ref("");
const Kelas = ref("");
const KelasLengkap = ref("");
const Jurusan = ref("");
const Tingkatan = ref("");
const Keperluan = ref("");

async function handleSubmit() {
  if (Keanggotaan == "Siswa") KelasLengkap.value = `${Tingkatan.value} ${Jurusan.value} ${Kelas.value}`;
  else KelasLengkap.value = "";
  const { error } = await supabase.from("perpusDigital").insert([
    {
      nama: Nama.value,
      anggota: Keanggotaan.value,
      kelas: KelasLengkap.value,
      keperluan: Keperluan.value,
    },
  ]);

  if (error) throw error;
  else navigateTo("/");
}
</script>

<style scoped>
@import url("https://fonts.googleapis.com/css2?family=Poppins:wght@400;500;900&display=swap");
@import url("https://fonts.googleapis.com/css2?family=Libre+Baskerville:wght@700&family=Poppins:wght@400;500;900&display=swap");

bg-color {
  background: #abdcff;
}

label {
  color: white;
  font-family: "Poppins", sans-serif;
}

h2 {
  font-family: "Libre Baskerville", serif;
  font-family: "Poppins", sans-serif;
}

.form {
  margin-bottom: 200px;
}

::placeholder {
  color: black;
}

.btn-biru {
  background: #3cadff;
}
</style>
