<script setup>
import { date } from 'astro/zod';
import { ref } from 'vue';

let msg = ref ('soy tooltip');
let checked = ref (false)

let data = ["hola", "mundo", "cruel"]

let filtered =data.filter(function (word){
    return word.includes('o')
})

</script>

<template>
    <input 
    class="border"
    :class="{'border-orange-400' : checked}"
    v-model="msg"
    
    >
   <div  :title="msg">     <!--  v-bind: -->
       {{ msg }}
    </div>
    <label for="checked">seleccionado {{ checked }}</label>
    <input type="checkbox" v-model="checked">

    <ul>
        <li v-for="(text, index) in filtered" :key="index">
        {{ text }}
        </li>
    </ul>
</template>