<template>
<div class="container">
        <transition name="fade">
        <div class="card" v-if="humidityHum != ' '">
            <div class="card-body">
                <h5 class="card-title">Humidity</h5>
                <p class="card-text">{{ humidityHum }} %</p>
            </div>
        </div>
    </transition>
</div>

</template>

<script>
export default {
    name: 'Humidity',

    props:['humidityHum'],

}
</script>