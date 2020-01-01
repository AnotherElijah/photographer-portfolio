<template>
    <div class="gallery-main-wrapper">
        <div v-for="(pic, i) in _gallery" v-bind:key='i' ref="picWrapper" class="small-picture"
             :class="(i+1)%2===0?'w-37':'w-31'"
             v-bind:style="{backgroundColor: '#967f65', backgroundImage: `url(${pic.urls.regular})`}"
             v-on:click="()=>_largePictureIndex=i"
        >
        </div>
        <div class="large-picture-wrapper" v-if="_largePictureIndex!==false">
            <LargePicture
                     v-bind:link="_gallery[_largePictureIndex].urls.regular"
                    :start="_largePictureIndex===0"
                    :end="_gallery.length-1===_largePictureIndex"
                    v-on:closeLgPic="_largePictureIndex = false"
                    v-on:nextLgPic="++_largePictureIndex"
                    v-on:prevLgPic="--_largePictureIndex"
            >
            </LargePicture>
        </div>
        <loader v-if="loader"></loader>
    </div>
</template>

<script>
    import LargePicture from "./LargePicture";
    import Loader from "../lib/loader";

    export default {
        name: "Gallery-section",
        components: {Loader, LargePicture},
        props: ['currentSection'],
        data() {
            return {
                gallery: '',
                largePictureIndex: false,
                loader: false
            }
        },
        computed: {
            _gallery:
                {
                    set: function (data) {
                        this.gallery = data
                    },
                    get: function () {
                        return this.gallery
                    }
                },
            _largePictureIndex:
                {
                    set: function (data) {
                        this.largePictureIndex = data
                    },
                    get: function () {
                        return this.largePictureIndex
                    }
                }
        },
        methods: {
            fetchImg(page) {

                setTimeout(() => {
                    if (this._gallery === '') return this.loader = true
                }, 200);

                fetch('https://api.unsplash.com/photos/?client_id=1aa14b0d65ca677d1d33cb57f30f1cba5456a8792b4c52ab4924a7e6b537d408&page=' + page)
                    .then(response => response.json())
                    .then(response => {
                        this._gallery = response;
                        setTimeout(() => this.loader = false, 600);
                    })

            },
        },
        created() {
            this.fetchImg(this.currentSection);
        },
    }
</script>

<style scoped>

    .w-31 {
        width: 30%;
        overflow: hidden;
        margin: 2px;
    }

    .w-37 {
        width: 33%;
        overflow: hidden;
        margin: 2px;
        flex-grow: 1;
    }

    .small-picture {
        height: 30vh;
        min-height: 200px;
        background-repeat: no-repeat;
        background-size: cover;
        background-position: center center;
    }

    .gallery-main-wrapper {
        display: flex;
        flex-wrap: wrap;
        position: relative;
        width: 100%;
    }

    .large-picture-wrapper {
        display: flex;
        flex-direction: column;
        justify-content: center;
        position: fixed;
        width: 100%;
        height: 100vh;
        padding: 8px;
        top: 0;
        left: 0;
        background-color: #111111;
        z-index: 16;
    }
</style>
