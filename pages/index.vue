<template>
  <div class="row">
    <div class="col">
      <table class="table table-striped">
        <thead>
          <tr>
            <th>#</th>
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
            <td>
              <span v-if="item.kelas">{{ item.kelas }}</span>
              <span v-else>-</span>
            </td>
            <td>{{ item.keperluan }}</td>
            <td>{{ item.tanggal }}</td>
          </tr>
        </tbody>
      </table>
    </div>
    <div class="div-col-lg">
      <select name="" id=""></select>
    </div>
  </div>
</template>

<script setup>
const supabase = useSupabaseClient();
const items = ref([]);
async function ambilData() {
  let { data, error } = await supabase.from("perpusDigital").select();
  if (error) throw error;
  if (data) items.value = data;
}

onMounted(() => {
  ambilData();
});
</script>

<style scoped></style>
