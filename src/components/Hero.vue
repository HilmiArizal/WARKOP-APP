<template>
  <div class="row">
    <div class="col">
      <div class="d-flex h-100">
        <div class="justify-content-center align-self-center">
          <h2>
            <strong>Delicious Food Menu, </strong> <br />
            in your gadget!
          </h2>
          <p>Ayo segera pilih pesanan favorite anda sekarang</p>
          <router-link class="btn btn-lg btn-primary" to="foods">
            <b-icon-arrow-right /> Pesan
          </router-link>
        </div>
      </div>
    </div>
    <div class="col">
      <img src="../assets/images/Food-icon.png" width="500" />
    </div>
  </div>
</template>

<script>
import "../assets/css/Hero.css";

export default {
  name: "Hero",
};
</script>

<style></style>
