<template>
  <div class="parent">
    <div class="orderBtn">
        <input type="button" :id="product.id" @click="buy()"/>
        <label :for="product.id"><div class="productName">{{product.name}}</div><div class="productPrice">{{product.price}}円</div></label>
    </div>
  </div>
</template>

<script>
export default {
  name: "orderButton",
  props:['product'],
  data() {
    return {
        
    };
  },
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