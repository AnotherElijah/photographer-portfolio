<template>
    <div class="gallery-main-wrapper">
        <div v-for="(pic, i) in _gallery" v-bind:key='i' ref="picWrapper" class="def-h"
             :class="(i+1)%2===0?'w-37':'w-31'"
        >
            <a href="#"><img :src='pic.urls.small' alt=""></a>
        </div>
    </div>
</template>

<script>
    export default {
        name: "Gallery-section",
        props: ['currentSection'],
        data() {
            return {
                gallery: '',
                galleryIndex: 0
            }
        },
        computed: {
            _gallery:
                {
                    set: function(data){
                        this.gallery = data
                    },
                    get: function(){
                        return this.gallery
                    }
                }
        },
        methods: {
            fetchImg(page){
                fetch('https://api.unsplash.com/photos/?client_id=1aa14b0d65ca677d1d33cb57f30f1cba5456a8792b4c52ab4924a7e6b537d408&page='+page)
                    .then(response=>response.json())
                    .then(response=> (this._gallery = response))
            },
        },
        created() {
            this.fetchImg(this.currentSection);
        },
    }
</script>

<style scoped>
    .def-h{
        height: 200px;
    }
    .gallery-main-wrapper{
        /*display: flex;*/
        /*flex-wrap: wrap;*/
        display: grid;
    }
    .w-31{
        width: 28%;
        overflow: hidden;
        padding: 4px;
        flex-grow: 1;
    }
    .w-37{
        width: 36%;
        overflow: hidden;
        padding: 4px;
        flex-grow: 1;
    }
</style>
