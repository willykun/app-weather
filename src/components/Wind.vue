<template>
<div class="container">
    <transition name="fade">
        <div class="card" v-if="windSpeed != ' '">
            <div class="card-body">
                <h5 class="card-title">Wind</h5>
                <p class="card-text"><strong>Speed </strong> {{ windSpeed }} m/s</p>
            </div>
        </div>
    </transition>
</div>
</template>

<script>
export default {
    name: 'Wind',

    props:['windSpeed'],

}
</script>