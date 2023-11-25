<template>
  <div>
    <div id="carouselExampleIndicators" class="carousel slide" data-bs-ride="true">
      <div class="carousel-indicators">
        <button type="button" data-bs-target="#carouselExampleIndicators" data-bs-slide-to="0" class="active" aria-current="true" aria-label="Slide 1"></button>
        <button type="button" data-bs-target="#carouselExampleIndicators" data-bs-slide-to="1" aria-label="Slide 2"></button>
        <button type="button" data-bs-target="#carouselExampleIndicators" data-bs-slide-to="2" aria-label="Slide 3"></button>
      </div>
      <div class="carousel-inner">
        <div class="carousel-item active">
          <img src="~/assets/buku1.jpg" class="d-block w-100" alt="..." />
        </div>
        <div class="carousel-item">
          <img src="~/assets/bukuu3.jpg" class="d-block w-100" alt="..." />
        </div>
        <div class="carousel-item">
          <img src="~assets/11buku1.jpg" class="d-block w-100" alt="..." />
        </div>
      </div>
      <button class="carousel-control-prev" type="button" data-bs-target="#carouselExampleIndicators" data-bs-slide="prev">
        <span class="carousel-control-prev-icon" aria-hidden="true"></span>
        <span class="visually-hidden">Previous</span>
      </button>
      <button class="carousel-control-next" type="button" data-bs-target="#carouselExampleIndicators" data-bs-slide="next">
        <span class="carousel-control-next-icon" aria-hidden="true"></span>
        <span class="visually-hidden">Next</span>
      </button>
    </div>
    <br />
    <div class="row justify-content-center">
      <div class="col-3">
        <img src="~assets/mtk.png" class="card-img-top" alt="..." />
        <div class="card-body">
          <h5 class="card-title">Buku Matematika</h5>
          <!-- <p class="card-text">Some quick example text to build on the card title and make up the bulk of the card's content.</p> -->
          <a href="#" class="btn btn-primary">Detail</a>
        </div>
      </div>
      <div class="col-3">
        <img src="~assets/ppkn.png" class="card-img-top" alt="..." />
        <div class="card-body">
          <h5 class="card-title">Buku PPKN</h5>
          <!-- <p class="card-text">Some quick example text to build on the card title and make up the bulk of the card's content.</p> -->
          <a href="#" class="btn btn-primary">Detail</a>
        </div>
      </div>
      <div class="col-3">
        <img src="~assets/infor.png" class="card-img-top" alt="..." />
        <div class="card-body">
          <h5 class="card-title">Buku Informatika</h5>
          <!-- <p class="card-text">Some quick example text to build on the card title and make up the bulk of the card's content.</p> -->
          <a href="#" class="btn btn-primary">Detail</a>
        </div>
      </div>
    </div>
  </div>
</template>
