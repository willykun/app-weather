<template>
    <div class="container">
        
            <div class="col-sm-12">
                <transition name="fade">
                    <div class="card" v-if="co != ' '">          
                        <div class="card-body">                   
                            <h5  class="card-title">Pollution</h5>  
                            <div class="row d-flex justify-content-center">
                                <div class="col-xs-6">
                                    <ul>
                                        <li> <strong>Carbon monoxide (CO)</strong>  {{ co }}</li>
                                        <li> <strong>Nitrogen monoxide (NO)</strong> {{ no }}</li>
                                        <li> <strong>Nitrogen dioxide (NO2)</strong> {{ no2 }}</li>
                                        <li> <strong>Ozone (O3) </strong> {{ o3 }}</li>
                                    </ul>
                                </div>
                                <div class="col-xs-6">
                                    <ul>
                                        <li> <strong>Sulphur dioxide (SO2)</strong> {{ so2 }}</li>
                                        <li> <strong>Ammonia (NH3) </strong> {{ nh3 }}</li>
                                        <li> <strong>Particulates PM2.5</strong>  {{ pm2_5 }}</li>
                                        <li> <strong> Particulates  PM10 </strong>{{ pm10}}</li>
                                    </ul>
                                </div>
                            </div>


                        </div>
                    </div>
                </transition>
            </div>
   
    </div>
</template>

<script>
export default {
    name: 'Pollution',

    props:['co', 'no', 'no2', 'o3', 'so2', 'nh3', 'pm2_5', 'pm10'],

}
</script>

<style scoped>
    .fade-enter-active, .fade-leave-active {
    transition: opacity 1s
    }
    .fade-enter, .fade-leave-to /* .fade-leave-active below version 2.1.8 */ {
    opacity: 0
    }

    ul >li  {
    list-style-type: none;
    }
.card {
    background: rgb(36,34,37);
    background: -moz-linear-gradient(59deg, rgba(36,34,37,0.9724264705882353) 0%, rgba(79,68,82,1) 49%, rgba(133,129,133,1) 100%);
    background: -webkit-linear-gradient(59deg, rgba(36,34,37,0.9724264705882353) 0%, rgba(79,68,82,1) 49%, rgba(133,129,133,1) 100%);
    background: linear-gradient(59deg, rgba(36,34,37,0.9724264705882353) 0%, rgba(79,68,82,1) 49%, rgba(133,129,133,1) 100%);
    filter: progid:DXImageTransform.Microsoft.gradient(startColorstr="#242225",endColorstr="#858185",GradientType=1);

}
</style>
</script>