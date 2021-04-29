<template>
    <div class="container">
            <transition name="fade">
                <div class="card" v-if="name">          
                    <div class="card-body">                   
                        <h5  class="card-title">City {{ name }}</h5>            
                    </div>
                </div>
            </transition>
        </div>
</template>

<script>
export default {
    name: 'City',

    props:['name'],

}
</script>