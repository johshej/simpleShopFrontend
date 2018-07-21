<template>
  <div id="app">
    <CurrencyMenu/>
    <ProductList/>
  </div>
</template>

<script>
import CurrencyMenu from './components/CurrencyMenu'
import ProductList from './components/ProductList'

export default {
  name: 'App',
  components: {
    CurrencyMenu,
    ProductList
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
