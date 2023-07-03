<script setup>
import Search from './components/Search.vue'
import Result from './components/Result.vue'

import { ref } from 'vue';


const result = ref([])

function search(ISBN){
    fetch("https://api.openbd.jp/v1/get?isbn=" + ISBN.value).then
    ( r=> r.json().then(json => {
        console.log(json);
        if(json[0] != null){
          result.value.unshift(json[0]);
        } 
    }),
    r => console.log("通信失敗")
    )
}

</script>

<template>
<header>
  <h1>本を検索</h1>
  <Search @response="ISBN => search(ISBN) "/>
</header>
<main>
  <Result :result = result />
</main>
</template>

<style scoped>
header {
  padding: 4em 0;
  background: #4169e1;
}
h1 {
  margin: .5em 0;
  text-align: center;
  color: #fff;
}
main {
  max-width: 60em;
  margin: auto;
  padding: 2em;

}
</style>
