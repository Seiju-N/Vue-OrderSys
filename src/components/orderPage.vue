<template>
  <div class="outline">
    <div class="panel">
      <div class="title">
        商品リスト
      </div>
      <order-button v-for="product in products" :key="product.name" :product="product" @buy="buy(product)"></order-button>
    </div>
    <div class="panel">
      <div class="title">
        お会計
      </div>
      <div>
        {{ count }}
      </div>
      <div>
        {{ totalPrice }}
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

const coffee : drink = {
  id:"coffee",
  name:"コーヒー",
  price:480,
}
const tea : drink = {
  id:"tea",
  name:"紅茶",
  price:280,
}
const milk : drink = {
  id:"milk",
  name:"ミルク",
  price:180,
}
const coke : drink = {
  id:"coke",
  name:"コーラ",
  price:190,
}
const beer : drink = {
  id:"beer",
  name:"ビール",
  price:580,
}

let products : Array<drink> = [coffee, tea, milk, coke, beer];
let cart : Array<drink> = [];

@Options({
  components: { orderButton },
  props: {
  },
  data(){
    return {
      products : products,
      totalPrice : 0,
      count : 0,
    }
  },
  methods:{
    buy(product : drink){
      cart.push(product);
      console.log(cart.length);
      this.totalPrice += product.price;
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
