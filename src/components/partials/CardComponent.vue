<template>
    <div class="col d-flex flex-column align-items-center g-5">
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
        'canzone': Object
    }
}
</script>

<style scoped lang="scss">
    img {
        width: 150px;
        height: 150px;
    }
    h2 {
        color: #fff;
        text-align: center;
        height: 50px;
        font-size: 1rem;
        margin-top: 10px;
    }
    .author, .date {
        color: lightgray;
        text-align: center;
        font-size: 0.8rem;
    }
</style>