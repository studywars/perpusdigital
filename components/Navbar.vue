<template>
  <div>
    <nav class="navbar navbar-expand-lg" style="background-color: #5daee7">
      <div class="container-fluid">
        <a class="navbar-brand" href="#">
          <img src="~/assets/Logo.png" alt="" />
        </a>
        <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarNavAltMarkup" aria-controls="navbarNavAltMarkup" aria-expanded="false" aria-label="Toggle navigation">
          <span class="navbar-toggler-icon"></span>
        </button>
        <div>
          <h2>Perpuskaan Digital</h2>
        </div>
        <div class="collapse navbar-collapse" id="navbarNav">
          <ul class="navbar-nav ms-auto">
            <li class="nav-item">
              <NuxtLink class="nav-link" aria-current="page" to="/home">Home</NuxtLink>
            </li>
            <li class="nav-item">
              <NuxtLink class="nav-link" to="/tambah">Isi Kunjungan</NuxtLink>
            </li>
            <li class="nav-item">
              <NuxtLink class="nav-link" to="/">Riwayat</NuxtLink>
            </li>
          </ul>
        </div>
      </div>
    </nav>
  </div>
  <!-- <nav class="navbar navbar-expand-lg navbar-dark shadow fixed-top" style="background-color: #030119">
    <div class="container">
      <a class="navbar-brand" href="#"> <img src="~/assets/Logo.png" alt="" width="30" height="33" class="d-inline-block align-text-top left-20" /></a>
      <h4 class="text-light pt-1">Perpus Digital</h4>
      <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarNavAltMarkup" aria-controls="navbarNavAltMarkup" aria-expanded="false" aria-label="Toggle navigation">
        <span class="navbar-toggler-icon"></span>
      </button>
      <div class="collapse navbar-collapse" id="navbarNavAltMarkup">
        <div class="navbar-nav ms-auto">
          <NuxtLink class="nav-link" aria-current="page" to="/">Home</NuxtLink>
          <NuxtLink class="nav-link" to="/pengunjung">Pengunjung</NuxtLink>
        </div>
      </div>
    </div>
  </nav> -->
</template>

<style scoped>
@import url("https://fonts.googleapis.com/css2?family=Poppins:wght@400;500;900&display=swap");
@import url("https://fonts.googleapis.com/css2?family=Libre+Baskerville:wght@700&family=Poppins:wght@400;500;900&display=swap");

ul {
  font-family: kadwa;
  font-size: 25px;
}

nav {
  background: #3cadff;
  color: white;
}
</style>
