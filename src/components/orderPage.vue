<template>
  <div class="outline">
    <div class="panel">
      left
    </div>
    <div class="panel">
      right
    </div>
  </div>
</template>

<script lang="ts">
import { Options, Vue } from 'vue-class-component';

type drink = {
  name:string;
  price:number;
}

const coffee : drink = {
  name:"コーヒー",
  price:480,
}
const tea : drink = {
  name:"紅茶",
  price:280,
}
const milk : drink = {
  name:"ミルク",
  price:180,
}
const coke : drink = {
  name:"コーラ",
  price:190,
}
const beer : drink = {
  name:"ビール",
  price:580,
}

@Options({
  props: {
  }
})
export default class orderPage extends Vue {
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
@import "../css/orderPage.css";
</style>
