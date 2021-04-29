<template>
    <div class="container">
            <transition name="fade">
                <div class="card" v-if="weatherDescription != ' '">
                    <div class="card-body">    
                        <h5 class="card-title"><img class="img img-fluid" v-bind:src="'https://openweathermap.org/img/w/'+ weatherIcon +'.png'" alt=""/>  Wheather {{ weatherMain }}</h5>
                        <p class="card-text"><strong>Description</strong> {{ weatherDescription }}</p>
                    </div>
                </div>
            </transition>
    </div>
</template>

<script>
export default {
    name: 'Weather',

    props:['weatherMain', 'weatherDescription', 'weatherIcon'],

}
</script>