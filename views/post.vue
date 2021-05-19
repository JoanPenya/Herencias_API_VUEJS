<template>
    <div id="post">
        <h1>{{$route.params.id}}</h1>
        
        <h1>{{$route.params.name}}</h1>

        <img v-bind:src="$route.params.img" v-bind:alt="$route.params.name">

        <p>edad: {{$route.params.age}} </p>
        <p>Muerto? {{$route.params.Death}} </p>
        
    </div>
</template>

<script>

</script>

<style>

</style>
