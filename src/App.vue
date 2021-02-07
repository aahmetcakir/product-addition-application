<template>
  <div class="container">
    <h1 class="text-center">Ürün Ekleme Uygulaması</h1>
    <hr />
    <new-product></new-product>
    <br /><br />
    <progress-bar></progress-bar>
    <br /><br />
    <h3 class="text-center">Eklenen Ürünlerin Listesi</h3>
    <hr />
    <products></products>
  </div>
</template>

<script>
import AddImage from "./components/AddImage.vue";
import NewProduct from "./components/NewProduct.vue";
import Products from "./components/Products.vue";
import ProgressBar from "./components/ProgressBar.vue";
export default {
  components: {
    NewProduct,
    ProgressBar,
    AddImage,
    Products,
  },


};
</script>

<style>
body {
  background-color: aliceblue;
  padding-top: 20px;
  padding-bottom: 20px;
}

.card {
  margin-right: 5px;
  margin-bottom: 5px;
}

.card:last-child {
  margin-right: 0px;
}

.col-md-2 {
  max-width: 15.666667% !important;
}

.product-container {
  margin-left: 15px;
}
</style>

