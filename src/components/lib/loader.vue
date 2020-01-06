<template>
    <div class="loader-wrapper" :class="showUp?'showUp':''">
        <img :src="require('@/assets/91.svg')" alt="">
    </div>
</template>

<script>
    export default {
        name: "loader",
        props: ['showUp']
    }
</script>

<style scoped>
    .loader-wrapper{
        position: absolute;
        width: 100vw;
        height: 100vh;
        visibility: hidden;
    }
    .loader-wrapper{
        width: 100vw;
        height: 100vh;
        position: fixed;
        top: 0;
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        background: #101010;
        left: 0;
        opacity: 0.6;
    }
    .showUp{
        visibility: visible;
    }
</style>