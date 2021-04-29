<template>
    <div class="container">
        <div class="row">
            <div class="col-sm-12">
                <city :name="name" ></city>
            </div>
        
            <div class="col-xs-12 col-sm-6">
                <weather :weatherMain="weatherMain" :weatherDescription="weatherDescription" :weatherIcon="weatherIcon"></weather>
            </div>

            <div class="col-xs-12 col-sm-6">
                <temperature :temperatureTemp="temperatureTemp" :temperatureFeels="temperatureFeels" :temperatureMin="temperatureMin" :temperatureMax="temperatureMax" ></temperature>
            </div>

            <div class="col-xs-12 col-sm-6">
                <humidity :humidityHum="humidityHum"></humidity>
            </div>
            <div class="col-xs-12 col-sm-6">
                <visibility :visibility="visibility"></visibility>
            </div>

            <div class="col-xs-12 col-sm-6">
                <wind :windSpeed="windSpeed"></wind>
            </div>
            
            <div class="col-xs-12 col-sm-6">
                <clouds :clouds="clouds"></clouds>
            </div>
        </div>
    </div>
</template>

<script>
import City from '../components/City';
import Weather from '../components/Weather';
import Humidity from '../components/Humidity';
import Visibility from '../components/Visibility';
import Temperature from '../components/Temperature';
import Wind from '../components/Wind';
import Clouds from './Clouds.vue';



export default {
    name: 'Dashboard',

    components:{
        City, Weather, Humidity, Visibility, Temperature, Wind, Clouds
    },
 
    props:['name', 'visibility', 'weatherMain', 'weatherDescription', 'weatherIcon', 'temperatureTemp', 'temperatureFeels', 'temperatureMin', 'temperatureMax', 'humidityHum', 'windSpeed', 'clouds'],

}
</script>

<style>
    .fade-enter-active, .fade-leave-active {
    transition: opacity 1s
    }
    .fade-enter, .fade-leave-to /* .fade-leave-active below version 2.1.8 */ {
    opacity: 0
    }
</style>