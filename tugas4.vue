<script setup>

import { ref } from 'vue'

const angka = ref()
let hasil = ref()
const isClicked = ref(false)
const Ganti = ref(true)

function hitung() {
    hasil.value = new Function(`return ${angka.value}`)();
    
}

function Gantiwarna() {
    isClicked.value = !isClicked.value
}

function toggle() {
    Ganti.value = !Ganti.value
}

</script>

<template>

<input type ="text" placeholder="masukkan angka" v-model="angka" >
<button @click="hitung">Hitung</button>

<br><br>

<div>{{ angka }}</div>
<div>{{ hasil }}</div>

<h1 :class="isClicked ? 'title-Clicked' : 'title'">HELLO WORLD</h1>
<button @click="Gantiwarna">Ganti Warna</button>

<button @click="toggle">Toggle</button>
<h1 v-if="Ganti">BENAR</h1>
<h1 v-else>SALAH</h1>


</template>

<style scoped>
.title {
    color: red;
}
.title-Clicked {
    color: blue;
}
</style>