<template>
  <div class="parent">
    <div class="orderBtn">
        <input type="button" :id="product.id" @click="buy()"/>
        <label :for="product.id" class="badge" :count="count[product.id]"><span class="productName">{{product.name}}</span><span class="productPrice">{{product.price}}円</span></label>
    </div>
  </div>
</template>

<script>
export default {
  name: "orderButton",
  props:['product','count'],
  methods:{
    buy(){
      this.$emit("buy",this.product);
    }
  }
};
</script>

<style scoped>
    @import "../../css/orderButton.css";
</style>