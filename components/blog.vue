<template>
    <div id="blog">
    <h1>Mi Blog</h1>

    <div
      v-for="currency in info"
      :key="currency.id"
      class="character"
    >
        <img v-bind:src="currency.img" v-bind:alt="currency.name">
        <span class="lighten">
          <router-link :to="{name: 'Post', params: {id: currency.id, name: currency.name, age: currency.Age, alliance: currency.alliance, origin: currency.origin, Death: currency.Death, img: currency.img}}">{{currency.name}}</router-link>
        </span>
      </div>
  </div>
</template>

<script>

import datos from '../snk.json';

export default {
    name: 'blog',
    computed: {
        info() {
        return datos.map((currency) => {
            return currency;
        })
        }
    },
}
</script>

<style>

</style>