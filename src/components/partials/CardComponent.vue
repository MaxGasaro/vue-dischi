<template>
    <div class="col-2 g-4">
        <img :src="canzone.poster">
        <h2>{{canzone.title}}</h2>
        <div class="author">{{canzone.author}}</div>
        <div class="date">{{canzone.year}}</div>
    </div>
</template>

<script>
export default {
    name: 'CardComponent',
    props: {
        'canzone': String
    }
}
</script>

<style scoped lang="scss">
    img {
        width: 200px;
        height: 200px;
    }
    h2 {
        color: #fff;
        text-align: center;
        height: 50px;
        font-size: 1.2rem;
        margin-top: 10px;
    }
    .author, .date {
        color: lightgray;
        text-align: center;
    }
</style>