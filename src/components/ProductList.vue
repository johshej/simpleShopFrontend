<template>
  <div class="products">
    <h1>{{ title }}</h1>
    <ul>
      <li v-for="product in products" v-bind:key="product.id">
        name: {{ product.name }}
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'Products',
  data () {
    return {
      title: 'Produkter',
      products: [ { id: 1, 'name': 'bar' } ]
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
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
