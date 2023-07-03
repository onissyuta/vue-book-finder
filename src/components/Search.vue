<script setup>
import { ref } from 'vue'

const ISBN = ref("978-4088820118")

const emit = defineEmits(['response'])

function search(){
    if(ISBN != ""){
        emit('response', ISBN)
    }
    ISBN.value = ""
}
</script>


<template>
<form @submit.prevent = "search">
    <input type="text" v-model="ISBN" placeholder="ISBNを入力">
    <button>検索</button>
</form>
</template>


<style scoped>
form{
    text-align: center;
    line-height: 3em;
}
input {
    padding: 0 1em;
    background: #fff;
    border-radius: 4px;
}
button {
    margin: 0 0 0 1em;
    padding: 0 1em;
    background: #fff;
    border-radius: 4px;
}
</style>