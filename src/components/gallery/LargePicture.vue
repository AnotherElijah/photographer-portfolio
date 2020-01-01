<template>
    <div class="inner-container">
        <div class="ctrl-wrapper">
            <button :class="!start?'btn-bcw':'btn-bcw hidden'" v-on:click="prev"><img :src="require('@/assets/basic/back.svg')" alt=""></button>
            <button class="btn-cross" v-on:click="close"><img :src="require('@/assets/basic/cross.svg')" alt=""></button>
            <button :class="!end?'btn-frw':'btn-frw hidden'" v-on:click="next"><img :src="require('@/assets/basic/next.svg')" alt=""></button>
        </div>
        <img class="lg-image" :src="link" alt="">
    </div>
</template>

<script>
    export default {
        name: "LargePicture",
        props: ['link', 'end', 'start'],
        methods: {
            close() {
                this.$emit('closeLgPic')
            },
            prev() {
                this.$emit('prevLgPic')
            },
            next() {
                this.$emit('nextLgPic')
            }
        }
    }
</script>

<style scoped>
    .hidden{
        visibility: hidden;
    }

    .lg-image {
        width: auto;
        max-height: 100vh;
    }

    .inner-container {
        display: flex;
        flex-direction: row;
        justify-content: center;
        align-items: flex-end;
    }

    .ctrl-wrapper {
        position: absolute;
        width: 180px;
        bottom: 45px;
    }

    .btn-cross,
    .btn-bcw,
    .btn-frw {
        background-color: transparent;
        border: transparent;
        padding: 0;
    }

    .btn-bcw img,
    .btn-frw img,
    .btn-cross img {
        width: 24px;
    }
    .btn-cross,
    .btn-bcw,
    .btn-frw{
        background-color: transparent;
        background-size: cover;
        padding: 15px;
    }
</style>