<template>
  <div class="products">
    <h1>{{ title }}</h1>
    <ul>
      <li v-for="product in products" v-bind:key="product.id">
        <div class="name">{{ product.name }} passed value: {{ testValue }}</div>
        <div v-bind:class="{ selectedCurrency: currency == 'dkk', 'price': true }">{{ product.price_dkk }}<span class="uppercase">{{ currency }}</span></div>
        <div v-bind:class="{ selectedCurrency: currency == 'sek', 'price': true }">{{ product.price_sek }}<span class="uppercase">{{ currency }}</span></div>
        <div v-bind:class="{ selectedCurrency: currency == 'eur', 'price': true }">{{ product.price_eur }}<span class="uppercase">{{ currency }}</span></div>
        <div v-bind:class="{ selectedCurrency: currency == 'usd', 'price': true }">{{ product.price_usd }}<span class="uppercase">{{ currency }}</span></div>
      </li>
    </ul>
  </div>
</template>

<script>

export default {
  name: 'Products',
  props: ['currency'],
  data () {
    return {
      title: 'Produkter',
      products: [ ]
    }
  },
  created () {
    fetch('http://localhost:8000/products', {
      headers: {
        Accept: 'application/json'
      }
    })
      .then(response => response.json())
      .then(json => {
        this.products = json
      })
      .catch(error => {
        console.log('request failed', error)
      })
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
  margin: 10px;
}
a {
  color: #42b983;
}
.uppercase {
  text-transform: uppercase;
}
.price {
  display: none;
}
.selectedCurrency {
  display: block;
}
</style>
