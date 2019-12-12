<template>
    <div>
        <img :src="'../../assets/gallery/1/norway-4540666_1280-1.jpg'" alt="">
        <div v-for="pic in gallery" v-bind:key='pic'>
            <img :src='include(pic.url)' alt="">
        </div>
    </div>
</template>

<script>
    //массив ссылок
    export default {
        name: "Gallery-section",
        props: ['currentSection'],
        data() {
            return {
                gallery: this.picRequest(),
            }
        },
        methods: {
            include(url){
                return require('@/'+url)
            },
            picRequest() {
                let commonPath = 'assets/gallery/';
                let album = this.currentSection;
                console.log(this.currentSection);
                //TODO img request
                return [
                    {
                        url: commonPath+album+'/norway-4540666_1280-1.jpg',
                    },
                    {
                        url: commonPath+album+'/norway-4540666_1280-2.jpg',
                    },
                    {
                        url: commonPath+album+'/norway-4540666_1280-3.jpg',
                    },
                    {
                        url: commonPath+album+'/norway-4540666_1280-4.jpg',
                    }
                ]
            },
        },
        computed:{
        },
        created() {
        }
    }
</script>

<style scoped>

</style>
