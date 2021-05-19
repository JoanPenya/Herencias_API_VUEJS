<template>
    <div id="api">
        <h1>Personajes de SNK</h1>

        <section v-if="errored">
            <p>Lo sentimos, no es posible obtener la información en este momento, por favor intente nuevamente mas tarde</p>
        </section>

        <section v-else>
            <div v-if="loading">Cargando...</div>

            <div
            v-else
            v-for="currency in info"
            :key="currency"
            >
            <img v-bind:src="currency.img" v-bind:alt="currency.name">
            <span class="lighten">
                <router-link :to="{name: 'Post', params: {id: currency.id, name: currency.name, age: currency.Age, alliance: currency.alliance, origin: currency.origin, Death: currency.Death, img: currency.img}}">
                    <span v-html="currency.name"></span>
                </router-link>
            </span>
            </div>

        </section>
    </div>
</template>

<script>

import axios from 'axios';

export default {
    name: 'api',
    data () {
        return {
            info: null,
            loading: true,
            errored: false
        }
    },
    filters: {
        currencydecimal (value) {
            return value.toFixed(2)
        }
    },
    mounted () {
        axios
            .get('https://my-json-server.typicode.com/Joanutsu/SNK-JSON/SNK')
            .then(response => {
                this.info = response.data
            })
            .catch(error => {
                console.log(error)
                this.errored = true
            })
            .finally(() => this.loading = false)
    }
}
</script>

<style>

</style>