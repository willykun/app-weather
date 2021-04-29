<template>
<div class="container">
    <transition name="fade">
        <div class="card" v-if="clouds != ' '">
            <div class="card-body">
                <h5 class="card-title">Clouds</h5>
                <p class="card-text"><strong>Nubosity </strong> {{ clouds }} %</p>
            </div>
        </div>

        <div class="card" v-if="clouds == 0 && clouds !=' '">
            <div class="card-body">
                <h5 class="card-title">Heaven Clear</h5>
                <p class="card-text"><strong>Nubosity </strong> 0 %</p>
            </div>
        </div>

    </transition>
</div>
</template>

<script>
export default {
    name: 'Clouds',

    props:['clouds'],

}
</script>