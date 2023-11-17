<template>
  <div class="row justify-content-center">
    <div class="col-lg-4">
      <h2>Isi Buku Kunjungan</h2>
      <form @submit.prevent="handleSubmit">
        <div class="mb-3">
          <input v-model="Nama" type="text" class="form-control" placeholder="Masukan Nama" required />
        </div>
        <div class="mb-3">
          <select v-model="Keanggotaan" class="form-control" name="" id="" required>
            <option value="">Pilih Keanggotaan</option>
            <option value="Siswa">Siswa</option>
            <option value="Guru">Guru</option>
            <option value="Staff">Staff</option>
          </select>
        </div>
        <div class="mb-3" v-if="Keanggotaan == 'Siswa'">
          <input v-model="Kelas" type="text" class="form-control" placeholder="Masukan Kelas" required />
        </div>
        <div class="mb-3">
          <textarea v-model="Keperluan" class="form-control" name="" id="" cols="30" rows="10" placeholder="Tulis Keperluan" required></textarea>
        </div>
        <button type="submit">Kirim</button>
      </form>
    </div>
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
  KelasLengkap.value = `${Tingkatan.value} ${Jurusan.value} ${Kelas.value}`;
  const { error } = await supabase.from("perpusDigital").insert([
    {
      nama: Nama.value,
      anggota: Keanggotaan.value,
      kelas: KelasLengkap.value,
      keperluan: Keperluan.value,
    },
  ]);

  if (!error) throw error;
  else navigateTo("/kunjungan");
}
</script>

<style lang="scss" scoped>
@import url("https://fonts.googleapis.com/css2?family=Poppins:wght@400;500;900&display=swap");
@import url("https://fonts.googleapis.com/css2?family=Libre+Baskerville:wght@700&family=Poppins:wght@400;500;900&display=swap");

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
</style>
