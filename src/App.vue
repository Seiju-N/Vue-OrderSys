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
@import "./css/style.css";
</style>
