<template>
  <img alt="Vue logo" src="./assets/logo.png">
  <div>This is ordering system.</div>
  <order-page></order-page>
</template>

<script lang="ts">
import { Options, Vue } from 'vue-class-component';
import orderPage from './components/orderPage.vue';

@Options({
  components: {
    orderPage,
  },
})
export default class App extends Vue {}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
