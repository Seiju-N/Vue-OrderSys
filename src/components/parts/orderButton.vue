<template>
  <div class="parent">
    <div class="orderBtn">
        <button :id="product.id" @click="buy()"/>
        <label :for="product.id" class="badge">
          <span class="productName">{{product.name}}</span><span class="productPrice">{{product.price}}円</span>
          <div :id="product.id+'-count'" class="counter">{{count[product.id]}}</div>
        </label>
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