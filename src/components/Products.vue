<template>
  <div class="row product-container">
    <product v-for="product in ProductsList" :key="product">
      <div>
        <img
          class="card-img-top"
          :src="product.selectedImage"
          :alt="product.productName"
        />
        <div class="card-body">
          <h5 class="card-title">{{product.productName}}</h5>
          <small> <strong>Adet : </strong>{{product.productPiece}}  </small>
          <br />
          <small> <strong>Fiyat : </strong>{{product.productPrice}} TL </small >
          <br />
          <small> <strong>Tutar : </strong> {{product.productPrice * product.productPiece}} TL </small>
        </div>
      </div>
    </product>
  </div>
</template>

<script>
import { eventBus } from "../main";
import Product from "./Product.vue";

export default {
  components: { product: Product },
  data() {
    return {
      ProductsList: [],
    };
  },

  created() {
    eventBus.$on("itemAdded", (product) => {
      if (this.ProductsList.length<10) {
        this.ProductsList.push(product);
        console.log(this.ProductsList);
        eventBus.$emit("progress",this.ProductsList.length)
        }
      else{
        alert("yavas la gac tane alıyon")
      }
    });
  },
};
</script>

<style>
</style>