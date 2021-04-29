<template>
  <div id="app"> 

    <nav class="navbar navbar-expand-lg">
      <a class="navbar-brand" href="#">Wheather App</a>
      <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarNav" aria-controls="navbarNav" aria-expanded="false" aria-label="Toggle navigation">
        <span class="navbar-toggler-icon"></span>
      </button>
      <div class="collapse navbar-collapse" id="navbarNav">
        <ul class="navbar-nav">
                <li class="nav-item">
                  <a class="nav-link" href="#" @click.prevent="fetchData(4.6097,-74.0817)">Bogotá</a>
                </li>
                <li class="nav-item">
                  <a class="nav-link" href="#" @click.prevent="fetchData(6.2518,-75.5636)">Medellín</a>
                </li>
                <li class="nav-item">
                  <a class="nav-link" href="#" @click.prevent="fetchData(-16.5, -68.15)">La Paz</a>
                </li>
                <li class="nav-item">
                  <a class="nav-link" href="#" @click.prevent="fetchData(-0.2299, -78.5249)">Quito</a>
                </li>
                <li class="nav-item">
                  <a class="nav-link" href="#" @click.prevent="fetchData(40.4165, -3.7026)">Madrid</a>
                </li>
                <li class="nav-item">
                  <a class="nav-link" href="#" @click.prevent="fetchData(48.8534, 2.3488)">Paris</a>
                </li>
                <li class="nav-item">
                  <a class="nav-link" href="#" @click.prevent="fetchData(35.6895, 139.6917)">Tokio</a>
                </li>
        </ul>
      </div> 
    </nav>

  
      <dashboard  :name="this.name"
                  :weatherMain="this.weatherMain" 
                  :weatherDescription="this.weatherDescription" 
                  :weatherIcon="this.weatherIcon" 
                  :temperatureTemp="this.temperatureTemp" 
                  :temperatureFeels="this.temperatureFeels" 
                  :temperatureMin="this.temperatureMin" 
                  :temperatureMax="this.temperatureMax" 
                  :humidityHum="this.humidityHum" 
                  :windSpeed="this.windSpeed"
                  :clouds="this.clouds" 
                  :visibility="this.visibility"
                  ></dashboard>
      <pollution
            :co="this.co"
            :no="this.no"
            :no2="this.no2"
            :o3="this.o3"
            :so2="this.so2"
            :pm2_5="this.pm2_5"
            :pm10="this.pm10"
            :nh3="this.nh3"
      ></pollution>
  </div>
</template>

<script>
import Dashboard from './components/Dashboard';
import Pollution from './components/Pollution';
import axios from 'axios';



export default {
  name: 'app',
  components:{
    Dashboard, Pollution
  },
  data () {
    return {
      name:'',
      weatherMain: ' ',
      weatherDescription: ' ',
      weatherIcon: ' ',
      temperatureTemp: ' ',
      temperatureFeels: ' ',
      temperatureMin: ' ',
      temperatureMax: ' ',
      humidityHum: ' ',
      visibility:' ',
      windSpeed: ' ',
      clouds: ' ',
      co: ' ',
      no: ' ',
      no2:' ',
      o3:' ',
      so2: ' ',
      pm2_5:' ',
      pm10: ' ',
      nh3: ' ',
      lat:' ',
      lon:' '
    }
  },
  methods:{
    fetchData(lat, lon) {
      axios.get(`http://api.openweathermap.org/data/2.5/air_pollution?lat=${lat}&lon=${lon}&appid=c30ea4cb0ff5a435c36e648efd05cbda`)
           .then(({ data }) => {  
             this.setPollutionValues(data)
           }).catch(error => console.log(error))
     
      axios.get(`https://api.openweathermap.org/data/2.5/weather?lat=${lat}&lon=${lon}&appid=c30ea4cb0ff5a435c36e648efd05cbda`)
           .then(({ data }) => {  
             this.setWheaterValues(data)
           }).catch(error => console.log(error))
    },
    setWheaterValues(data){
        this.name = data.name,
        this.weatherMain= data.weather[0].main,
        this.weatherDescription= data.weather[0].description,
        this.weatherIcon= data.weather[0].icon,
        this.temperatureTemp=  data.main.temp,
        this.temperatureFeels=  data.main.feels_like,
        this.temperatureMin=  data.main.temp_min,
        this.temperatureMax=  data.main.temp_max,
        this.humidityHum=  data.main.humidity,
        this.windSpeed=  data.wind.speed,
        this.clouds=  data.clouds.all,
        this.visibility =  data.visibility
    },
     setPollutionValues(data){
        this.co = data.list[0].components.co,
        this.no = data.list[0].components.no,
        this.no2 = data.list[0].components.no2,
        this.o3 = data.list[0].components.o3,
        this.so2 = data.list[0].components.so2,
        this.pm2_5 = data.list[0].components.pm2_5,
        this.pm10 = data.list[0].components.pm10,
        this.nh3 = data.list[0].components.nh3
     }
  }
}
</script>

<style>
@import "../node_modules/bootstrap/dist/css/bootstrap.min.css";

#app, body{
background-color: black;
}

.navbar-nav a, .navbar-brand, nav-link{
  color:#fff;
}

 .navbar-nav a:hover{
  color:rgb(144,8,167)
}

img{
  width: 15%;
}

.card{
  border-radius: 1em;
  color: #fff;
  text-align: center;
  margin: 10px;
  background: rgb(144,8,167);
  background: -moz-linear-gradient(59deg, rgba(144,8,167,0.9724264705882353) 0%, rgba(179,24,209,1) 49%, rgba(248,0,255,1) 100%);
  background: -webkit-linear-gradient(59deg, rgba(144,8,167,0.9724264705882353) 0%, rgba(179,24,209,1) 49%, rgba(248,0,255,1) 100%);
  background: linear-gradient(59deg, rgba(144,8,167,0.9724264705882353) 0%, rgba(179,24,209,1) 49%, rgba(248,0,255,1) 100%);
  filter: progid:DXImageTransform.Microsoft.gradient(startColorstr="#9008a7",endColorstr="#f800ff",GradientType=1);
}

</style>


