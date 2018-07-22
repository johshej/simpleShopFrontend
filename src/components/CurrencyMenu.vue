<template>
  <div class="currencyMenu">
    <ul id="currencyList">
      <li>
        <a v-bind:class="{ active: currency == 'dkk' }" href="?currency=dkk">Danske kroner</a>
        <a v-bind:class="{ active: currency == 'sek' }" href="?currency=sek">Svenska kronor</a>
        <a v-bind:class="{ active: currency == 'eur' }" href="?currency=eur">Euro</a>
        <a v-bind:class="{ active: currency == 'usd' }" href="?currency=usd">Dollar</a>
      </li>
    </ul>
  </div>
</template>

<script>

export default {
  name: 'currencyList',
  props: ['currency']
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
  color: blue;
}
.active {
  color: #42b983;
}
</style>
