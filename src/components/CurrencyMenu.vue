<template>
  <div class="currencyMenu">
    <ul id="currencyList">
      <li>
        <a href="?currency=dkk">Danske kroner</a>
        <a href="?currency=sek">Svenska kronor</a>
        <a href="?currency=eur">Euro</a>
        <a href="?currency=usd">Dollar</a>
      </li>
    </ul>
    <div>cur {{ currency }}</div>
  </div>
</template>

<script>

// Get and set curreny
const params = (new URL(document.location)).searchParams
const currency = params.get('currency')
if (currency) {
  localStorage.setItem('simpleShopCurrency', currency)
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
