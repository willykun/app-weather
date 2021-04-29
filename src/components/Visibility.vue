<template>
<div class="container">
    <transition name="fade">
        <div class="card" v-if="visibility != ' '">
            <div class="card-body">
                <h5 class="card-title">Visibility</h5>
                <p class="card-text">{{ visibility }} m</p>
            </div>
        </div>
    </transition>
</div>
</template>

<script>
export default {
    name: 'Visibility',

    props:['visibility'],

}
</script>