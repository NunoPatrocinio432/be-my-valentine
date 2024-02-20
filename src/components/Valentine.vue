<script setup>
    import {ref} from 'vue'

    const yes = ref(false)
    const no = ref(false)

    function change()
    {
        no.value = true
        var b = document.querySelector("#noButton");
        b.className = "button-romantic mt-4 no-after";
        var i = Math.floor(Math.random()*1200)+1;
        var j = Math.floor(Math.random()*500)+1;
        b.style.left = i+"px";
        b.style.top = j+"px";
    }
</script>

<template>
    <div class="row" v-if="yes">
        <h1><b>YAYYYY!! I LOVE YOU!!! </b></h1>
    </div>
    <div class="row" v-else-if="no">
        <h1><b>You can't escape from my love </b></h1>
    </div>
    <div class="row" v-else>
        <h1><b>Do you want to be my Valentine?</b></h1>
    </div>
    <div class="row img-gif" v-if="yes">
        <img src="https://media1.tenor.com/m/_hUq1BSUsiMAAAAC/cat-cute.gif">
    </div>
    <div class="row img-gif" v-else-if="no">
        <img src="https://media1.tenor.com/m/sLIuJuqBfSYAAAAd/luna-cat-crunchy-cat.gif">
    </div>
    <div class="row" v-else>
        <img class= "img-gif" src="https://media1.tenor.com/m/KdYQAufJITUAAAAC/bingus-bingus-flower.gif">
    </div>
    <div class="row" v-if="!yes">
        <div class="col-6">
            <button class="button-romantic mt-4 mr-6"  @click="yes = !yes" role="button">YES</button>
        </div>
        <div class="col-6">
            <button class="button-romantic mt-4 no"  id="noButton" @mouseenter="change" role="button">NO</button>
        </div>
    </div>
</template>