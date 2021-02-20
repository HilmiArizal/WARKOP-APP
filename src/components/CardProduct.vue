<template>
  <div class="card shadow" id="card-product" style="width: 100%; min-height: 45vh;">
    <img
      :src="'assets/images/' + product.gambar"
      id="card-img-top"
      alt="..."
    />
    <div class="card-body">
      <div class="card-title">{{ product.nama }}</div>
      <p class="card-text">Harga : {{ product.harga }}</p>
      <footer>
        <a href="#" class="btn btn-primary btn-sm"
          ><b-icon-cart></b-icon-cart> Pesan</a
        >
      </footer>
    </div>
  </div>
</template>

<script>
import "../assets/css/CardProduct.css";

export default {
  name: "CardProduct",
  props: ["product"],
};
</script>

<style></style>
