<template>
  <div>
   <cart-products-list :cart="cart" ></cart-products-list>
  </div>
</template>

<script>
import { eventBus } from "../../main.js";
import CartProductsList from './CartProductsList.vue';

export default {
  components: { CartProductsList },
  data() {
    return {
      cart: []
    }
  },
  created() {
    this.cart = eventBus.cart;
    eventBus.$on("update:cart", (cart) => {
      this.cart = cart;
    });
  }
};
</script>

