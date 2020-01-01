<template>
    <div class="loader-wrapper">
        <img :src="require('@/assets/91.svg')" alt="">
    </div>
</template>

<script>
    export default {
        name: "loader",
    }
</script>

<style scoped>
    .loader-wrapper{
        position: absolute;
        width: 100vw;
        height: 100vh;
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
</style>