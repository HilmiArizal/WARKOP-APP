<template>
  <div>
    <Navbar />
    <div class="container">
      <div class="row mt-4">
        <div class="col">
          <h2>Daftar <strong> Makanan</strong></h2>
        </div>
      </div>

      <div class="row mt-3">
        <div class="col">
          <div class="input-group mb-3">
            <input
              v-model="search "
              type="text"
              class="form-control"
              placeholder="Cari makanan ..."
              aria-label="Username"
              aria-describedby="basic-addon1"
              @keyup="searchFood()"
            />
            <span class="input-group-text" id="basic-addon1">
              <b-icon-search></b-icon-search>
            </span>
          </div>
        </div>
      </div>

      <div class="row">
        <div
          class="col-md-3 mt-4"
          v-for="product in products"
          :key="product.idbestproduct"
        >
          <CardProduct :product="product" />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Navbar from "@/components/Navbar.vue";
import CardProduct from "@/components/CardProduct.vue";
import Axios from "axios";

export default {
  name: "Foods",
  components: {
    Navbar,
    CardProduct,
  },

  data() {
    return {
      products: [],
      search: "",
    };
  },
  methods: {
    setProduct(data) {
      this.products = data;
    },
    searchFood() {
      Axios.get("http://localhost:3000/products?q=" + this.search)
        .then((res) => this.setProduct(res.data))
        .catch((err) => console.log(err));
    },
  },

  mounted() {
    Axios.get("http://localhost:3000/products")
      .then((res) => this.setProduct(res.data))
      .catch((err) => console.log(err));
  },
};
</script>

<style></style>
