<template>
<div class="container">
    <transition name="fade">
        <div class="card" v-if="temperatureTemp != ' '">
            <div class="card-body">
                <h5 class="card-title">Temperature {{ temperatureTemp }} K</h5>
                <p class="card-text"> <strong>Feel like</strong> {{ temperatureFeels }}K - <strong>Max</strong>  {{ temperatureMax }}k - <strong>Min</strong> {{ temperatureMin }} K</p>
            </div> 
        </div>
    </transition>
</div>
</template>


<script>
export default {
    name: 'Temperature',

    props:['temperatureTemp', 'temperatureFeels', 'temperatureMax', 'temperatureMin'],

}
</script>