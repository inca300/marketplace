<template>
  <div>
   <shop-products-list :products="products" ></shop-products-list>
  </div>
</template>

<script>
import ShopProductsList from './ShopProductsList.vue';
import { eventBus } from "../../main.js";

export default {
  components: { ShopProductsList },
  data() {
    return {
      products: []
    }
  },
  created() {
    this.products = eventBus.products;
    eventBus.$on("update:products", (products) => {
      this.products = products;
    });
  }
};
</script>

