<script setup>
const props = defineProps({
    book: JSON
})
</script>

<template>
    <dt>タイトル</dt>
    <dd>{{ book.summary.title }}</dd>
    <dt>表紙</dt>
    <dd><img :src="book.summary.cover"></dd>
    <dt>著者</dt>
    <dd>{{ book.summary.author }}</dd>
    <dt>説明</dt>
    <dd>{{ book.onix.CollateralDetail.TextContent[0].Text }}</dd>
    <dt>出版年月</dt>
    <dd>{{ book.summary.pubdate }}</dd>
</template>

<style scoped>
dt {
    margin: 1em 0 0 0;
    font-weight: bold;
}
</style>