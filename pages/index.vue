<template>
  <div>
    <h2>Isi Buku Kunjungan</h2>
  </div>
  <div>
    {{ Nama }}
    <form @submit.prevent="handleSubmit">
      <div>
        <input v-model="Nama" type="text" placeholder="Masukan Nama" />
      </div>
      <div>
        <select v-model="Keanggotaan" name="" id="">
          <option value="">Pilih Keanggotaan</option>
          <option value="Siswa">Siswa</option>
          <option value="Guru">Guru</option>
          <option value="Staff">Staff</option>
        </select>
      </div>
      <div>
        <input v-model="Kelas" type="text" placeholder="Masukan Kelas" />
      </div>
      <div>
        <textarea v-model="Keperluan" name="" id="" cols="30" rows="10" placeholder="Tulis Keperluan"></textarea>
      </div>
      <button type="submit">Kirim</button>
    </form>
  </div>
</template>

<script setup>
const supabase = useSupabaseClient();
const Nama = ref("");
const Keanggotaan = ref("");
const Kelas = ref("");
const Keperluan = ref("");

async function handleSubmit() {
  const { data, error } = await supabase.from("perpusDigital").insert([
    {
      nama: Nama.value,
      angggota: Keanggotaan.value,
      kelas: Kelas.value,
      keperluan: Keperluan.value,
    },
  ]);

  if (!error) navigateTo("/kunjungan");
  else throw error;
}
</script>
