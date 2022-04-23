<template>
  <div class="outline">
    <div class="panel">
      left
      <order-button v-for="product in products" :key="product.name" :product="product" @buy="buy(product)"></order-button>
    </div>
    <div class="panel">
      right
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

@Options({
  components: { orderButton },
  props: {
  },
  data(){
    return {
      products : products,
    }
  },
  methods:{
    buy(product : object){
        console.log(product);
    }
  }
})
export default class orderPage extends Vue {
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
@import "../css/orderPage.css";
</style>
