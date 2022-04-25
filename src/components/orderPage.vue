<template>
  <div class="outline">
    <div class="panel left">
      <div class="title">
        商品リスト
      </div>
      <order-button v-for="product in products" :key="product.id" :id="product.name" :product="product" :count="product_count" @buy="buy(product)"></order-button>
    </div>
    <div class="panel right">
      <div class="panel-back">
        <div class="title">
          お会計
        </div>
        <div>
          商品数 : <span id="count">{{ count }}</span>
        </div>
        <div>
          合計金額 : <span id="price">{{ totalPrice }}</span>
        </div>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import { Options, Vue } from 'vue-class-component';
import orderButton from './parts/orderButton.vue';

type drink = {
  id:string;
  name:string;
  price:number;
}

let coffee : drink = {
  id:"coffee",
  name:"コーヒー",
  price:480,
}
let tea : drink = {
  id:"tea",
  name:"紅茶",
  price:280,
}
let milk : drink = {
  id:"milk",
  name:"ミルク",
  price:180,
}
let coke : drink = {
  id:"coke",
  name:"コーラ",
  price:190,
}
let beer : drink = {
  id:"beer",
  name:"ビール",
  price:580,
}

//商品リスト
let products : Array<drink> = [coffee, tea, milk, coke, beer];
//カート内の商品
let cart : Array<drink> = [];
//商品ごとの個数
let product_count : {[key:string]: number} = {};
products.forEach(function(product){
  product_count[product.id] = 0;
});


@Options({
  components: { orderButton },
  props: {
  },
  data(){
    return {
      products : products,
      totalPrice : 0,
      count : 0,
      product_count : product_count,
    }
  },
  methods:{
    buy(product : drink){
      cart.push(product);
      product_count[product.id] = product_count[product.id] + 1;
      this.totalPrice = cart.reduce((sum, pd) => sum + pd.price, 0);
      this.count = cart.length;
    }
  },
})
export default class orderPage extends Vue {
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
@import "../css/orderPage.css";
</style>
