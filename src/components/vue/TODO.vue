<script setup>
import { ref } from 'vue'

const todos = ref (['estudiar'])
const todo = ref('')

function add () {
    // console.log(todo.value)
    // todos.value.unshift(todo.value)
    // todo.value = ''
    if (todo.value.trim()) {
    todos.value.unshift(todo.value.trim())
    todo.value = ''
  }
}

function borrar (index) {
    todos.value.splice(index, 1)
}

</script>

<template>

<div class="rounded shadow-md bg-slate-200 max-w-96 mx-auto mt-12 py-6 px-5 cursor-default ">
    <div class="">
        <input v-model="todo" class="w-4/5 outline-none rounded px-2"/>
        <button @click="add" class="outline-none bg-lime-400 w-1/5 text-white text-center hover:bg-green-400">
            +
        </button>

        <div class="mt-3">
            <div v-for="(todo, i) in todos" :key="i" class="bg-orange-300 rounded px-2 py-1 flex justify-between mb-2">
                {{ todo }}

                <div class="space-x-1">
                    <button @click="borrar(index)" class="bg-red-700 outline-none text-white text-center rounded py-1 px-1">Borrar</button>
                    <button class="bg-yellow-300 outline-none text-white text-center rounded py-1 px-1">editar</button>
                </div>

            </div>
            
        </div>
    </div>
</div>    
</template>