<script setup>
import { ref } from 'vue';

const tasks = ref([])
const inputTask = ref('')

function addtask(){
    tasks.value.push(inputTask.value)
    console.log(tasks)
}


</script>

<template>
    <div class="max-w-96 bg-slate-300 rounded shadow mx-auto mt-10 px-8 py-10">
        <h1 class="text-lg text-center">Lista de Tareas</h1>
        <div class="mt-4 mb-2">
            <input v-model="inputTask" class="w-4/5" />
            <button @click="addtask" class="w-1/5 bg-green-500 text-white font-bold">+</button>
        </div>

        <div 
        v-for="(task,index) in tasks"
        :key="index"
         class="bg-white/60 px-2">{{task}}</div>
    </div>
</template>