<template>
  <div class="currencyMenu">
    <ul id="currencyList">
      <li>
        <a class="dkk" href="?currency=dkk">Danske kroner</a>
        <a class="sek" href="?currency=sek">Svenska kronor</a>
        <a class="eur" href="?currency=eur">Euro</a>
        <a class="usd" href="?currency=usd">Dollar</a>
      </li>
    </ul>
    <div>Selected currency: {{ currency }}</div>
  </div>
</template>

<script>

// Get and set curreny
const defaultCurrency = 'dkk'
const queryParameters = (new URL(document.location)).searchParams
let currency = queryParameters.get('currency')
if (currency) {
  localStorage.setItem('simpleShopCurrency', currency)
}
else if (localStorage.getItem('simpleShopCurrency')) {
  currency = localStorage.getItem('simpleShopCurrency')
}
else {
  currency = defaultCurrency
}

export default {
  name: 'currencyList',
  data: function () {
    return {
      currency: currency
    }
  }
}

</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: normal;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
