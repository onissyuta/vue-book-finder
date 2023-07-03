<script setup>
import Book from './Book.vue'

const props = defineProps({
    result: JSON
})

</script>

<template>
    <dl v-for="book in result">
        <Book :book = book />
    </dl>
</template>


<style scoped>
dl {
    margin: 3em 0;
    padding: 3em;
    background: #fff;
    border-radius: 8px;
}
</style>