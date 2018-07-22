<template>
  <div id="app">
    <CurrencyMenu :currency="currency"/>
    <ProductList :currency="currency"/>
  </div>
</template>

<script>
import CurrencyMenu from './components/CurrencyMenu'
import ProductList from './components/ProductList'

// Get and set currency
const defaultCurrency = 'dkk'
const queryParameters = (new URL(document.location)).searchParams
let currency = queryParameters.get('currency')
if (currency) {
  localStorage.setItem('simpleShopCurrency', currency)
} else if (localStorage.getItem('simpleShopCurrency')) {
  currency = localStorage.getItem('simpleShopCurrency')
} else {
  currency = defaultCurrency
}

export default {
  name: 'App',
  data: function () {
    return {
      currency: currency
    }
  },
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
