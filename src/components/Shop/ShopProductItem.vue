<template>
  <div class="w-25 product-container m-1 p-3 d-flex flex-column">
   <div class="d-flex flex-row justify-content-center">
     <img style="height:150px" :src="product.img" alt="macbook">
   </div>
   <div>
     <h3>{{ product.title }}</h3>
     <hr>
   </div>
   <div>
     <p>{{ product.description }}</p>
   </div>
   <div class="d-flex flex-row justify-content-between">
     <span>{{ product.price }}</span>
     <button class="btn btn-primary btn-sm" @click="addProductToCart">Commander</button>
   </div>
  </div>
</template>

<script>
import { eventBus } from "../../main.js";

export default {
  props: ["product"],
  methods: {
    addProductToCart() {
      eventBus.addProductToCart({ ...this.product });
    }
  }
}
</script>

<style>
  .product-container {
    height: 400px;
  }

  p {
    font-size: 12px;
  }
</style>